# Tweet Reply Mock API

A small Node.js + Express app that fetches a tweet by ID and posts a manual reply using the Twitter API.

## What It Does

- Exposes `POST /api/idol-functions/generateTweetReply`
- Reads a `tweetId` from the request body
- Fetches the original tweet text
- Prompts you in the terminal to type a reply
- Posts that reply as a threaded response

## Requirements

- Node.js 18+
- A Twitter/X developer app with user auth credentials

## Setup

1. Install dependencies:

```bash
npm install
```

2. Create your env file:

```bash
cp .env.example .env
```

3. Fill in `.env` values:

```env
TWITTER_API_KEY=
TWITTER_API_SECRET=
TWITTER_ACCESS_TOKEN=
TWITTER_ACCESS_SECRET=
TWITTER_BEARER_TOKEN=
```

## Run

Start the API server:

```bash
node server.js
```

Server runs on `http://localhost:4000`.

## API Usage

Endpoint:

```http
POST /api/idol-functions/generateTweetReply
Content-Type: application/json
```

Request body:

```json
{
  "tweetId": "YOUR_TWEET_ID"
}
```

Example with curl:

```bash
curl -X POST http://localhost:4000/api/idol-functions/generateTweetReply \
  -H "Content-Type: application/json" \
  -d '{"tweetId":"1234567890123456789"}'
```

After calling the endpoint, check the terminal and enter your reply when prompted.

## Quick Auth Test

You can verify credentials with:

```bash
node test.js
```

If successful, it prints your authenticated user info.

## Notes

- Current `npm test` is a placeholder and exits with an error by default.
- `server.js` and `test.js` use ES module syntax (`import ...`). Ensure your Node setup supports this.
