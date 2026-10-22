---
title: "Introducing Neru: Building My Second Application"
description: "A look into Neru (ねる), its architecture, and lessons learned from expanding beyond my first project."
pubDate: "2026-03-28"
tags: ["neru", "appdev", "projects"]
featured: true
---

After shipping Wammy, I wanted to push my engineering skills further. That curiosity led directly to **Neru (ねる)**.

## What Makes Neru Different

With Neru, my focus was on building a privacy-focused sleep and inactivity timer for Android:

- Modular and decoupled architecture in Kotlin and Jetpack.
- 100% offline, privacy-first, zero telemetry.
- Target app foreground activity tracking with smooth audio fade-out.

```kotlin
data class NeruTimerConfig(
  val targetApps: List<String>,
  val durationMinutes: Int,
  val fadeOutDurationSeconds: Int = 30
)

val config = NeruTimerConfig(
  targetApps = listOf("Spotify", "YouTube", "Instagram"),
  durationMinutes = 45
)
```

Building two full applications like Wammy and Neru helped bridge the gap between theoretical computer science and real-world software delivery.
