# Autonomous AI Content Pipeline

A fully automated, zero-touch AI content pipeline that runs daily — selecting videos and titles from a Google Sheet, generating contextual taglines using AI, embedding them onto the video, and publishing to YouTube without any human intervention.

## What It Does

Once deployed, this pipeline runs on a daily schedule and autonomously handles the entire content creation and distribution workflow:

1. **Data Fetch** — reads a list of video titles and pre-provided video files from a Google Sheet via the Google Sheets API
2. **Title Selection** — randomly picks a title/concept from the sheet
3. **Tagline Generation** — uses an LLM to generate a contextual tagline for the selected title
4. **Tagline Embedding** — overlays the generated tagline as text directly onto the corresponding video
5. **YouTube Publishing** — uploads the final video with embedded tagline to YouTube automatically via the YouTube Data API
6. **Scheduling** — the entire workflow runs on a daily cron schedule — no human input required after initial setup

## Architecture

```
Google Sheets (titles + video links)
        ↓
  Title & Video Selection
        ↓
  LLM Tagline Generation
        ↓
  Tagline Embedded onto Video
        ↓
  YouTube Auto-Publish
        ↓
  Daily Schedule Trigger
```

## Tech Stack

- **n8n** — workflow orchestration and automation
- **Google Sheets API** — title and video data source
- **YouTube Data API v3** — automated video publishing
- **LLM (via API)** — tagline generation
- **Video Processing** — tagline text overlay onto video

## Key Concepts Demonstrated

- Multi-step agentic AI pipeline design
- API orchestration across multiple services
- Automated media processing (text overlay on video)
- Zero-intervention automated content systems
- Scheduled automation with cron triggers

## Setup

1. Import the `workflow.json` into your n8n instance
2. Configure credentials for:
   - Google Sheets API
   - YouTube OAuth2
   - LLM API key
3. Add your video titles and video file links to the connected Google Sheet
4. Activate the workflow — it runs daily automatically

## Files

- `workflow.json` — full n8n workflow export, ready to import

---

**Author:** Vatsal Agrawal  
**GitHub:** [github.com/vatsal-agra](https://github.com/vatsal-agra)  
**LinkedIn:** [linkedin.com/in/vatsal-agrawal-a7a9641b0](https://linkedin.com/in/vatsal-agrawal-a7a9641b0)
