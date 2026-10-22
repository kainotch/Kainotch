---
title: "Building Wammy: An All-in-One Android Reader"
description: "How I built an all-in-one reader for manga, manhwa, and light novels with built-in sources and cloud synchronization."
pubDate: "2026-04-15"
tags: ["android", "kotlin", "wammy"]
featured: true
---

Wammy started out of a simple frustration: having to use three different apps to read manga, webtoons, and light novels, none of which synced my reading progress smoothly across devices.

I decided to build **Wammy** as an all-in-one open-source Android reader application.

## Key Features

- **Unified Library:** Manga, manhwa, and light novels side by side.
- **Built-in Content Sources:** Fast, clean scrapers and parsers.
- **Automatic Cloud Sync:** Seamless progress saving.

```kotlin
// Android cloud sync worker
class SyncWorker(context: Context, params: WorkerParameters) : CoroutineWorker(context, params) {
    override suspend fun doWork(): Result {
        return try {
            val syncRepository = SyncRepository()
            syncRepository.syncProgress()
            Result.success()
        } catch (e: Exception) {
            Result.retry()
        }
    }
}
```

Building Wammy taught me how to handle asynchronous operations, local caching with Room database, and writing clean Android architecture.
