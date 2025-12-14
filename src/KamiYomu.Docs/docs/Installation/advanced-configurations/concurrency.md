---
title: Concurrency
parent: Advanced Configurations
nav_order: 1
---

# Concurrency

KamiYomu provides several concurrency-related settings that allow you to fine‑tune how many background tasks and crawler agents instances can run in parallel. These options can be configured directly through your Docker Compose environment variables.

---
## Worker__WorkerCount

Defines the maximum number of background worker threads that Hangfire can run concurrently.  
Each worker is capable of executing **one task at a time**, such as scanning or downloading manga.

Increasing this value increases parallelism, but it also **significantly impacts system resources**.

### How it Works

- Each worker thread processes one background job.
- More workers = more jobs running at the same time.
- Concurrency improves throughput, but also increases:
  - CPU usage
  - Memory consumption
  - Disk and network activity

### Memory Considerations (Important)

Most crawler agents used by KamiYomu rely on **Chromium-based browsers** (via Puppeteer) to fetch and render content.

This has a **major impact on memory usage**:

- A single Chromium instance typically consumes **150–250 MB of RAM** while active.
- Each crawling task usually requires **its own Chromium instance**.
- This memory is consumed **per active worker**, not shared.

In practice:

- **1 worker** ≈ 200–300 MB RAM
- **3 workers** ≈ 600–900 MB RAM
- **5 workers** ≈ 1–1.5 GB RAM

Actual usage varies depending on:
- Website complexity
- Number of open tabs/pages
- Enabled browser features
- System libraries and OS


{: .danger }
> **Be careful when increasing `Worker__WorkerCount`.**  
> Each active worker may spawn a dedicated Chromium instance, which can consume **200 MB or more of memory per > task**.  
> On systems with limited RAM (such as VPS or Raspberry Pi), setting this value too high may cause:
> - Out-of-memory (OOM) kills
> - System slowdowns
> - Task failures or crashes
{: .danger }

### Recommended Guidelines

- **Low-memory systems (≤ 2 GB RAM)**  
  Set `Worker__WorkerCount` to **1**

- **Mid-range systems (4–8 GB RAM)**  
  Set `Worker__WorkerCount` to **2–3**

- **High-memory systems (16 GB+ RAM)**  
  Increase cautiously and monitor usage

Use `Worker__WorkerCount` to scale throughput **only if your hardware allows it**.  
When tuning this value, always consider Chromium’s memory footprint, not just CPU usage.

## Worker__MaxConcurrentCrawlerInstances

Specifies the maximum number of crawler instances that may run **simultaneously for the same source**.

- Commonly set to `1` to ensure only one crawler operates per source at a time.  
  This avoids duplicate work, race conditions, and potential rate‑limiting or blocking by the target site.
- You may increase this value if the source supports parallel requests and you want higher throughput.

### Important Notes

- **Worker__WorkerCount** controls the *total* number of worker threads available.
- **Worker__MaxConcurrentCrawlerInstances** limits how many of those threads can be used by a *single crawler type*.

### Examples

- **Worker__MaxConcurrentCrawlerInstances = 1**  
  **Worker__WorkerCount = 4**  
  → Up to 4 different crawler agents can run at the same time, but each agent runs only one instance.

- **Worker__MaxConcurrentCrawlerInstances = 2**  
  **Worker__WorkerCount = 6**  
  → Each crawler agent may run up to 2 instances concurrently,  
    and up to 3 different crawler agents can be active simultaneously.

---

These settings allow you to balance performance, resource usage, and source‑specific constraints to best fit your deployment environment.


{% capture docker_full_example_note %}
{% include note-docker-full-example.md %}
{% endcapture %}
{{ docker_full_example_note | markdownify }}