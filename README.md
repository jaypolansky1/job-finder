# Job Finder

Job Finder aggregates job listings from across the web to highlight technical writing, developer advocate, and Learning & Development (L&D) roles.

## Overview

This Application Programming Interface (API) seeks to streamline the job application process by making it easier to find open roles.

## Base URL

https://job-scraper.replit.app/

## Authentication

The API uses API-key authentication.

` X-API-Key: your-generated-api-key
`

API keys are issued by the API owner upon request.

Keep API keys private. Do not include them in public code or screenshots.

## Quick Start

Make your first request:

```
curl "[BASE_URL]/[ENDPOINT]' \
-H "[HEADER-NAME]: [YOUR_API_KEY]"
```

A successful response returns:

```
  {
  "[field]": "[example value]"
  }
```

For example:

```
  {
  "location": "Atlanta"
  }
```



