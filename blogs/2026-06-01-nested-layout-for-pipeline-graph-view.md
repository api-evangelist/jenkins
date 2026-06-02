---
title: "Nested layout for pipeline graph view"
url: "https://www.jenkins.io/blog/2026/06/01/nested-layout-for-pipeline-graph-view/"
date: "2026-06-01"
feed_url: "https://www.jenkins.io/rss.xml"
---
We’re happy to announce that the most requested feature for the Pipeline Graph View plugin (and for Blue Ocean before it) is finally here: a new layout that renders nested pipelines in full detail. Pipelines with nested parallel stages (like CI → Run tests → Frontend → cypress above) or nested sequential stages (like CD above) benefit from this change the most. Upgrade the Pipeline Graph View plugin to version 918.vf572523124f2 or later to use the new layout.
