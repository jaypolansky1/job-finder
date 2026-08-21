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

Job Finder's public API lets you retrieve current job listings from selected companies, review statistics on where available jobs are located, and check the aggregator status. Every endpoint requires an `X-API-Key` header.

| Method | Endpoint | Purpose |
| --- | --- | --- |
| GET | ` /api/healthz ` | Health check | 
| GET | ` /api/jobs ` | Retrieve job listing data |
| GET | ` /api/jobs/stats ` | Display statistics on jobs available in the database | 
| POST | ` /api/scrape/run ` | Start aggregating manually |
| GET | ` /api/scrape/status ` | Check the status of an aggregation run |
| GET | ` /api/companies ` | List all companies that are included in the database |
| POST | ` /api/companies ` | Add a company to be included in the database |
| PATCH | ` /api/companies/:id ` | Update a target company |
| DELETE | ` /api/companies/:id ` | Remove a target company |
