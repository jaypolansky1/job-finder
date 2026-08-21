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

## Endpoints

### Purpose

## Health Check

```

GET /api/healthz

```

### Job statistics

```

GET /apijobs/stats

```

### Dashboard job listing data

```

GET /api/jobs

```

### Dashboard job statistics

```

GET /api/stats

```

### Start a scrape manually

```

GET /api/scrape/run

```

### Check a scrape's progress

```

GET /api/scrape/status

```

### List all companies with available jobs

```

GET /api/companies

```

### Add a target company

```

POST /api/companies

```

### Update a company's target

```

PATCH /api/companies/:id

```

### Remove a company's target

```

DELETE api/companies/:id

```
