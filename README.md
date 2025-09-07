# qmtry-rss-top-story-curator

# 📰 QMTRY — RSS Top Story Curator 🎯✨  
**Turn Headlines into Gold. Automatically. Auditably. Charmingly.**

![QMTRY Badge](https://img.shields.io/badge/QMTRY-Audit_Ready_Teal?style=flat-square&logo=dependabot)  
![Status](https://img.shields.io/badge/status-Live-brightgreen?style=flat-square)  
![Sentiment](https://img.shields.io/badge/sentiment-scored-blueviolet?style=flat-square)

---

## 💡 Short Description  
**Curated healthcare RSS feeds → ranked by relevance → styled and spun into a carousel of influence.**  
This repo powers [QMTRY.ai](https://qmtry.ai)'s homepage carousel with 6 top healthcare stories daily, ranked by sentiment, keywords, and visual appeal — delivered via Python + Synology cron + WordPress magic.

---

## 📖 What is This and Why Should You Care?

In the sea of AI hype and healthcare buzzwords, **QMTRY** is your lighthouse. 🏝️  
This repo automates a *serious-but-sexy* stack:

- 📬 **RSS ingestion** from curated healthcare sources  
- 🧠 **Sentiment scoring** using VADER — yes, the NLP one, not Darth  
- 🎨 **Image & summary extraction** (because ugly feeds are a crime)  
- 🎯 **Top 6 story filtering** based on keywords, categories, and vibes  
- 🧼 **JSON export** → `/wp-content/uploads/rss/rss_top.json`  
- 🌀 **Auto-rotating WordPress carousel** with badges, dates, and shimmer effects  
- 🔁 **Synology cron job automation** — no more manual refreshes  
- 📈 **Logging + monitoring** for audit-readiness

**✨ Outcome?**  
You get a homepage carousel that makes visitors go:  
_"Whoa, who curates this feed? This site actually *cares* about what’s happening."_ 😎

---

## 🛠️ Tech Stack

| Component        | Description                                      |
|------------------|--------------------------------------------------|
| `qmtry_rss_collector.py` | RSS ingest, VADER scoring, filtering |
| `rss_top.json`   | Final curated list of stories (6 max)           |
| `run_rss_collector.sh` | Cron-executed script on Synology NAS |
| `cron_log.txt`   | Output for debugging/logging sanity checks      |
| WordPress Shortcode | Displays the carousel via `[qmtry_top_rss]` |
| Synology Task Scheduler | Automates daily runs at 07:00 AM         |

---

## 🔁 Workflow Diagram

```mermaid
flowchart TD
  A[📡 RSS Feeds] --> B[🔍 Python RSS Collector]
  B --> C[🧠 Sentiment + Keyword Ranking]
  C --> D[🎨 Image + Summary Extraction]
  D --> E[📦 rss_top.json]
  E --> F[🌀 WordPress Carousel]
  F --> G[🌐 Displayed to Human Eyeballs]
  H[🕑 Cron Job (Synology)] --> B
  B --> I[📓 cron_log.txt]
