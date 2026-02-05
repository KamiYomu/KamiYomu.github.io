---
title: Download Mangas
parent: Getting Started
nav_order: 2
---


# Download Mangas

For downloading Manga, you need to [Install a crawler agent]({{ 'docs/crawler-agents/install-crawler-agents' | relative_url }}) in KamiYomu.

1. Go to Download
1. Select the installed crawler agent
1. Type the name of manga, then click on search

<img src="{{ '/assets/tutorial/search-mangas.gif' | relative_url }}" height="300"/>

1. Click on Actions
1. Select "Add to your collection" (this action will start the download process)

<img src="{{ '/assets/tutorial/download-mangas.gif' | relative_url }}" height="300"/>

1. Click on Your Collection
1. On your manga that is downloaded: Click on Actions
1. Click on "Download Status"
1. You can see the progress of your manga download

<img src="{{ '/assets/tutorial/see-collection-mangas.gif' | relative_url }}" height="300"/>


## Advanced Settings

## 📂 Set Up Your Download

Before adding a manga to your download queue, click the **'Set Up Your Download'** button to customize how your files are organized.

### Custom Path & Naming
You can manually define the naming convention for your library. This allows you to use specific folder structures or filenames that fit your personal preference. You can also utilize **Template Variables** to automate this process.

### Merging Collections
The setup panel allows you to **merge folders** with existing manga in your library. When merging:
* The system will use the existing configuration of the selected manga.
* New chapters will be routed to the same directory to keep your collection unified.

### Default Configurations
If no custom values are provided, the system uses the defaults defined in your `environment variables` or `appsettings.json` file.

**Default Templates:**
* **Path:** `{manga_title}/{manga_title} Ch.{chapter_padded_4}`
* **Title:** `{manga_title} Ch.{chapter_padded_4}`
* **Series:** `{manga_title}`

You can save this customization as your preferred setting by selecting the option `Make this the default setting for future collections.`.
New manga download will following these settings.

### Template Variables Reference

| Variable | Category | Sample Value |
| :--- | :--- | :--- |
| `{manga_title}` | Manga | KamiYomu: The Sample 2 |
| `{manga_title_slug}` | Manga | kamiyomu:-the-sample-2 |
| `{manga_familysafe}` | Manga | True |
| `{chapter}` | Chapter | 1 |
| `{chapter_padded_1}` | Chapter | 1 |
| `{chapter_padded_2}` | Chapter | 01 |
| `{chapter_padded_3}` | Chapter | 001 |
| `{chapter_padded_4}` | Chapter | 0001 |
| `{chapter_padded_5}` | Chapter | 00001 |
| `{chapter_title}` | Chapter | Romance Sideways |
| `{chapter_title_slug}` | Chapter | romance-sideways |
| `{volume}` | Chapter | 1 |
| `{volume_padded_1}` | Chapter | 1 |
| `{volume_padded_2}` | Chapter | 01 |
| `{volume_padded_3}` | Chapter | 001 |
| `{volume_padded_4}` | Chapter | 0001 |
| `{volume_padded_5}` | Chapter | 00001 |
| `{date}` | Date and Time | 2026-02-04 |
| `{date_short}` | Date and Time | 2026-02-04 |
| `{date_compact}` | Date and Time | 20260204 |
| `{time}` | Date and Time | 21-15-23 |
| `{time_compact}` | Date and Time | 211523 |
| `{datetime}` | Date and Time | 2026-02-04 21-15-23 |
| `{datetime_compact}` | Date and Time | 20260204_211523 |
| `{year}` | Date and Time | 2026 |
| `{month}` | Date and Time | 02 |
| `{day}` | Date and Time | 04 |
| `{hour}` | Date and Time | 21 |
| `{minute}` | Date and Time | 15 |
| `{second}` | Date and Time | 23 |

<img src="{{ '/assets/setup-your-download.jpeg' | relative_url }}" height="300"/>

## See your PDF/Zip files

1. Open "Chapters Found" table click on it
1. Click on Actions
1. If download of chapters has been completed, you can download it in different formats
    - PDF
    - Zip
    - CBZ (Which is a zip file)

<img src="{{ '/assets/tutorial/download-chapter-pdf.gif' | relative_url }}" height="300"/>


{% capture manga_file_note %}
{% include note-manga-file.md %}
{% endcapture %}
{{ manga_file_note | markdownify }}


{% capture download_status_note %}
{% include note-download-status.md %}
{% endcapture %}
{{ download_status_note | markdownify }}