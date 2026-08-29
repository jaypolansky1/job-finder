# I Created An API to Learn How to Document One

Application Programming Interface (API) Documentation. As I look for my next role in technical writing, I read job posting after job posting looking for someone to create developer-facing documentation. And those kinds of roles invariably require experience documenting APIs. The challenge is that most of my experience in technical writing, up until now, has had a focus of client-facing documentation. Knowledge base articles. Product announcement emails.

My goal was to create clear and usable content that was accessible. I crafted sentence after sentence to make complex software easy to use for non-technical (or, at least, non-developer) audiences. Since I always worked from software as it was designed for end users, I had not had the chance to work from the perspective of developers and more technical users by documenting APIs. I recently decided to change that, as I had built some side projects, and I could (or, at least, Replit could) create APIs out of them.

## Keys and Endpoints

Enter Job Finder.

As part of my search for a new role, I built an aggregation tool that searches through company websites (instead of, say, LinkedIn or Indeed) for jobs. This software scans through the career pages of these websites and seeks roles that match job titles that I specified, with technical writing roles included as one of many related and adjacent fields.

You have to manually start the aggregator, but, once it starts working and finds a post that meets my criteria, it will add a row to a table with the role name, company name, link, and a few more data points. That is the user experience as it works on my Replit-hosted website. To expand the side project into an API, I just prompted Replit’s AI agent to add an API for the app. Then, I deployed the app again to pick up the changes. Easy. Now for the documentation part.

I wasn’t sure of the best way to document an API, so I asked Replit to create an outline. However, I instructed the AI to not fill out the details, even though it could, and, it would if I did not instruct it otherwise. This way the agent could provide the structure, while I could learn by filling in the details (with a little help from the agent, of course.) I ended up with the following sections for my API documentation:

* Base URL
* Authentication
* Quick Start
* Endpoints
* Errors
* Rate Limits
* Data Freshness
* Contact

To authenticate with the app, users would request an API key from me, but, in reality, the API was really meant for me for documentation purposes. Essentially,  I was creating a key for myself. Users (or myself) would authenticate this way:

`X-API-Key: YOUR_API_KEY`

The interesting thing I learned about keys is not all APIs use the same name for the key. When I went to test an API in Postman that I didn’t create, I was surprised that the key had a slightly different name. Live and learn, I guess, but that small experience made me value good, well-written documentation even more.

My API had a few endpoints, which were designed to retrieve job listings from the app, along with retrieving some statistics like the number of jobs aggregated and from which platform they were sourced. I also added an endpoints for the number of jobs available in each location, which, of course, isn’t always 100 percent clear. I documented only GET Requests because the goal of the project was to keep the project simple and I was only really intending the API to pull data. I was not looking to POST data because any changes I would need to make (like add new target companies) I would likely do through Replit’s AI agent itself.

| Method | Endpoint | Purpose |
| --- | --- | --- |
| GET | `/api/v1/jobs` | Retrieve and filter current job listings. |
| GET | `/api/v1/jobs/stats` | Display job totals and platform breakdown. | 
| GET | `/api/v1/locations` | Display the number of jobs available in each location. |
| GET | `/api/v1/status` | Check the aggregator's latest run. |
| GET | `/api/v1/openapi.json` | Download the API definition. |

## Testing The API

To test the API, and ensure all of the endpoints were working properly, I signed up for Postman. The sign-up process was incredibly simple, and I was up and running in no time. (Side note: When I think of Postman, I think of that old song from the 60’s.) It was kind of a thrill to do my first API calls and have the API return data like a job posting from Hacker News instead of reviewing it from my app’s User Interface (UI) itself. I am so used to experiencing software from the end user experience: you just click a button or a link and data displays in rows and tables. Having the data returned to me in code was something else:

```json

{
    "jobs": [
        {
            "id": 236,
            "title": "Technical content developer",
            "company": "Klara Systems",
            "platform": "hackernews",
            "location": "Remote",
            "isRemote": true,
            "salaryRaw": null,
            "url": "https://news.ycombinator.com/item?id=49161851",
            "postedAt": "2026-08-03T21:43:16.000Z",
            "scrapedAt": "2026-08-19T20:04:53.339Z",
            "searchTerm": "technical content developer"
        }
     ],
    "total": 1,
    "page": 1,
    "pageSize": 1
}

```

To test the less-than-ideal use cases, I made my own mistakes to experience the errors for myself. After all, not everything goes according to plan, and someone newer to APIs (like me!) who is using my APIs is prone to make mistakes every now and then. Well, maybe *more* than every now and then, but at least they have AI agents to assist them. For instance, to generate an error code, I tried pulling some information using an endpoint that didn’t exist and received the below message:


``` {
    "error": {
        "code": "NOT_FOUND",
        "message": "The requested public API endpoint does not exist."
    }
}
```

And, of course, I tried submitting a GET Request without providing my key and the result was as expected:


``` {
    "error": {
        "code": "UNAUTHORIZED",
        "message": "A valid API key is required."
    }
}
 ```

## Lessons
 
All in all, I think my first experience with documenting APIs was a success. I think if I had to take any lessons away from it, they would be the below:

* I would recommend that anyone who wants to gain technical skills beyond what they learned in previous roles is to simply build something for yourself. And then document it. It’s always more interesting to document something that you have an interest in and documenting a job search API was a perfect fit for someone looking for a job.
* I would also recommend letting an AI agent guide you but not do the work. Have the AI agent outline the docs but not write them outright (it’s fully capable of doing, so I instructed it specifically not to write the docs for me.) This approach provides much-needed structure, while it still allows you to do the work.

Now that I have shared my experience, I would love to have your feedback. How have you learned how to document APIs? Have you created an app with an API to learn how to create developer documentation? If you are already an API expert, how have you learned something new for technical writing? Are you learning by doing like me, or do you prefer to dive into the docs, a book, or a tutorial? Reach out to me at `jay@technicalwriting.io`.




