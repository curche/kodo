---
description: >-
  Tracking helps you automatically send read manga chapters to supported
  trackers, so you can keep track of what and when you read it online.
---

# Tracking

Tracking is currently supported on [MyAnimeList](https://myanimelist.net/), [AniList](https://anilist.co/), [Kitsu](https://kitsu.io/), [Shikimori](https://shikimori.one/), and [Bangumi](https://bangumi.tv/)

* Tracking must be done **manually** for every manga.
* You must read the last page of a chapter to mark the chapter as read and track it.
* You can manually set the chapter by tapping on the number and then entering the number in or dragging the ticker up or down.
* After being offline, Tachiyomi will send progress made offline to the tracker.
* Tachiyomi will attempt to automatically set the start date when starting a manga.
* Tachiyomi will also set the finished date and reading status to completed if the read chapter is equal to the tracker's total chapters.
* Tracking is one-way. Meaning updating status in Tachiyomi will update the tracker, but updating status in the tracker will not update Tachiyomi.

Unattended tracking is also supported for [Komga](https://komga.org/), and works a bit differently from other trackers:

* You don't need to login into the tracker, it uses the credentials from your Komga extension.
* Tracking is done automatically, you don't have to search and bind every manga.
* Tracking only works for the Komga sources.
* Tracking is two-way, and local chapters will be marked as read.
* You must read the last page of a chapter to mark the chapter as read and track it.
* If you mark a chapter as read manually, the tracker will not be updated right away. You can update the tracker status on the server-side by opening the tracker sheet.
* You can configure Tachiyomi to automatically track manga when adding to the library. Go to **More → Settings → Tracking** and then **Track silently when adding manga to the library**

### How do I login into trackers? <a href="#how-do-i-login-into-trackers" id="how-do-i-login-into-trackers"></a>

1. Go to **More → Settings → Tracking** to Login
2. Tap the tracker you would like to login to, it will automatically open the browser and lead you through the login process.

### How do I set up tracking for each manga? <a href="#how-do-i-set-up-tracking-for-each-manga" id="how-do-i-set-up-tracking-for-each-manga"></a>

1. Go to the manga you want to track.
2. Tap the Tracking button.
3.  Tap **Add tracking** on the service you want to track the manga on.

    > _You can also change the search query if there is no match._

### How do I log in with Kitsu? <a href="#how-do-i-log-in-with-kitsu" id="how-do-i-log-in-with-kitsu"></a>

To log in with Kitsu, you need to use your email address as your username.

### Why am I unable to find a manga in MAL's search results? <a href="#why-am-i-unable-to-find-a-manga-in-mal-s-search-results" id="why-am-i-unable-to-find-a-manga-in-mal-s-search-results"></a>

If you cannot find a manga by name, you can look it up on MAL and then search for it in Tachiyomi using the following format: `id:<id from manga URL>`. You can also search for a manga on your MAL profile list by searching in the following format: `my:<manga name>`.

{% hint style="info" %}
Related GitHub issue: [#65](https://github.com/tachiyomiorg/tachiyomi/issues/65)
{% endhint %}

### How do I see which manga I have or have not tracked in my library? <a href="#how-do-i-see-which-manga-i-have-or-have-not-tracked-in-my-library" id="how-do-i-see-which-manga-i-have-or-have-not-tracked-in-my-library"></a>

Go to Library  → Tap Filter on the top right → Go to the Filter tab and toggle Tracked. If you are logged into more than one tracker, toggle the tracker you want to include or exclude.
