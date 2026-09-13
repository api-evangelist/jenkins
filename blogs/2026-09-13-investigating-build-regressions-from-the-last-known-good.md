---
title: "Investigating Build Regressions From the Last Known-Good Build"
url: "https://www.jenkins.io/blog/2026/09/10/investigating-build-regressions-from-the-last-known-good-build/"
date: "2026-09-13"
feed_url: "https://www.jenkins.io/rss.xml"
---
The following scenario is a case study. A Jenkins build fails in an integration test. The console contains a NoSuchMethodError, so the immediate task seems straightforward: find the incompatible dependency.
