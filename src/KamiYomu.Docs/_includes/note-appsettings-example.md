
```jsonc
{
    "Kestrel": {
        "Endpoints": {
            "Http": {
                // Kestrel HTTP listener URL. Change only if you need a different host or port.
                // Docker environment variable: Kestrel__Endpoints__Http__Url
                "Url": "http://*:8080"
            }
        }
    },
    // Serilog logging configuration (leave empty to use defaults).
    // Equivalent docker env: Serilog__<SETTING_NAME>
    "Serilog": {},
    "AllowedHosts": "*", // Comma-separated allowed hostnames. Docker: AllowedHosts
    // Connection strings point to local database file paths by default.
    // Equivalent docker envs: ConnectionStrings__AgentDb, ConnectionStrings__ReadingDb, ConnectionStrings__ImageDb, ConnectionStrings__WorkerDb
    "ConnectionStrings": {
        "AgentDb": "/db/main.db", // Crawler Agent database (primary)
        "ReadingDb": "/db/reading.db", // Manga reader database
        "ImageDb": "/db/image.db", // Image cache database
        "WorkerDb": "/db/worker.db" // Background jobs database
    },
    // Paths for special folders. Prefer absolute paths when running in Docker and bind-mount host folders.
    // Equivalent docker envs: SpecialFolders__LogDir, SpecialFolders__AgentsDir, SpecialFolders__DbDir, SpecialFolders__MangaDir
    "SpecialFolders": {
        "LogDir": "/logs", // Log directory (update Serilog accordingly when changed)
        "AgentsDir": "/agents", // Crawler agents folder
        "DbDir": "/db", // Database folder (ensure it matches ConnectionStrings paths)
        "MangaDir": "/manga",  // Download destination for manga
        "FilePathFormat": "{manga_title}/{manga_title} Ch.{chapter_padded_4}", // File organization pattern
        "ComicInfoTitleFormat": "{manga_title} ch.{chapter_padded_4}",
        "ComicInfoSeriesFormat": "{manga_title}"
    },
    "StartupOptions": {
        // Default UI language (e.g. "en"). Docker: StartupOptions__DefaultLanguage
        "DefaultLanguage": "en",
        // Default search term shown in UI. Docker: StartupOptions__DefaultSearchTerm
        "DefaultSearchTerm": "CrawlerAgents",
        // Family safe mode enabled/disabled. Docker: StartupOptions__FamilySafeMode
        "FamilySafeMode": true
    },
    "BasicAuth": {
        // Enable basic auth for the web UI. Docker: BasicAuth__Enabled
        "Enabled": false,
        // Admin username/password for basic auth. Docker: BasicAuth__AdminUsername, BasicAuth__AdminPassword
        "AdminUsername": "",
        "AdminPassword": ""
    },
    "Chromium": {
        // Optional download URL for bundled Chromium. Docker: Chromium__DownloadUrl
        "DownloadUrl": null,
        // Executable name for Chromium/Chrome (e.g. "chrome" or path). Docker: Chromium__ExecutableName
        "ExecutableName": "chrome"
    },
    "Worker": {
        // Available server names for background workers. Docker: Worker__ServerAvailableNames (comma-separated or JSON array)
        "ServerAvailableNames": [
            "KamiYomu-background-1"
        ],
        // Number of worker threads/processes. Docker: Worker__WorkerCount
        "WorkerCount": 2,
        // Max concurrent crawler instances per worker. Docker: Worker__MaxConcurrentCrawlerInstances
        "MaxConcurrentCrawlerInstances": 1,
        // Backoff/wait periods (ms). Docker: Worker__MinWaitPeriodInMilliseconds, Worker__MaxWaitPeriodInMilliseconds
        "MinWaitPeriodInMilliseconds": 3000,
        "MaxWaitPeriodInMilliseconds": 7001,
        "MaxRetryAttempts": 10,
        // Queue names used by background processing. Docker: Worker__DownloadChapterQueues, Worker__MangaDownloadSchedulerQueues, Worker__DiscoveryNewChapterQueues
        "DownloadChapterQueues": [
            "download-chapter-queue-1"
        ],
        "MangaDownloadSchedulerQueues": [
            "manga-download-scheduler-queue-1"
        ],
        "DiscoveryNewChapterQueues": [
            "discovery-new-chapter-queue-1"
        ]
    }

}

```