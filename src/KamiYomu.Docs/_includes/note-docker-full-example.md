
See below the full example of docker file with all applied configurations:

```yml
services:
  kamiyomu:
    image: marcoscostadev/kamiyomu:latest # Check releases for latest versions
    ports:
      - "8080:8080" # HTTP Port
    environment:
        # Basic Authentication
        BasicAuth__Enabled: false,
        BasicAuth__AdminUsername: "dev"
        BasicAuth__AdminPassword: "dev"
        # Startup configuration
        StartupOptions__DefaultLanguage: "en"
        StartupOptions__DefaultSearchTerm: "CrawlerAgents" # Add-ons search term
        StartupOptions__FamilySafeMode:  true # initialize as family safe mode
        # Default path template
        SpecialFolders__FilePathFormat: "{manga_title}/{manga_title} Ch.{chapter_padded_4}"
        SpecialFolders__ComicInfoTitleFormat: "{manga_title} ch.{chapter_padded_4}"
        SpecialFolders__ComicInfoSeriesFormat: "{manga_title}"
        # Worker configurations
        Worker__WorkerCount: 2
        Worker__MaxConcurrentCrawlerInstances: 1
        Worker__MinWaitPeriodInMilliseconds: 3000
        Worker__MaxWaitPeriodInMilliseconds: 9001
        Worker__MaxRetryAttempts: 10
        Worker__ServerAvailableNames__0:   "KamiYomu-background-1" 
        Worker__DownloadChapterQueues__0:  "download-chapter-queue-1" 
        Worker__MangaDownloadSchedulerQueues__0:  "manga-download-scheduler-queue-1" 
        Worker__DiscoveryNewChapterQueues__0:  "discovery-new-chapter-queue-1" 
    restart: unless-stopped
    healthcheck:
      test: ["CMD", "curl", "-f", "http://localhost:8080/healthz"]
      interval: 30s
      timeout: 10s
    volumes:
      - manga_storage:/manga 
      - database_storage:/db 
      - logs_storage:/logs 
      - crawler_agents:/agents 
      - /etc/localtime:/etc/localtime:ro
volumes:
  manga_storage:
  database_storage:
  logs_storage:
  crawler_agents:
```