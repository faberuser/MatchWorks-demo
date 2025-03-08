# MatchWorks Server

Document: <a href="https://documenter.getpostman.com/view/27360970/2sAYBbepYm#1021f2c3-5af9-424a-9ed1-1e95926c82b6" target="_blank">Postman</a>

## Installation

### Initialize Database

1.  Create new MongoDB on [Atlas](https://cloud.mongodb.com/)
2.  Copy database URI with password
    `mongodb+srv://username:password@cluster0.example.mongodb.net`
3.  Download [MongoDB Database Toolt](https://www.mongodb.com/try/download/database-tools)
4.  Run

    ```bash
    mongorestore --uri <connection string> /path/to/dump
    ```

    _refer the `/path/to/dump` as /dump in this directory_

5.  Create `.env` at `/server` file with these fields

    ```bash
    SERVER_PORT=8080
    MONGO_URI=your-mongo-uri
    ACCESS_TOKEN_SECRET=mw_access_token_secret
    ACCESS_TOKEN_LIFE=30m
    REFRESH_TOKEN_SECRET=mw_refresh_token_secret
    REFRESH_TOKEN_LIFE=30d
    GEMINI_API_KEY=your-gemini-api-key
    ```

### Local Server Installation

1. Install

```bash
npm i
```

2. Run

```bash
npm run dev
```

### Docker

1. Build

```bash
docker-compose build
```

2. Run

```bash
docker-compose up
```

## Production

### Manual

1. Install

```bash
npm ci
```

2. Build

```bash
npm run build
```

3. Run

```bash
npm start -- --port 8080
```

### Docker

1. Pull repo

```bash
docker pull s3975162/matchworks-server:latest
```

2. Run

-   Windows

```bash
docker run -e CLIENT_URL="http://localhost:5173" -e MONGO_URI="your-mongo-uri" -e GEMINI_API_KEY="your-gemini-api-key" -e ACCESS_TOKEN_SECRET="mw_access_token_secret" -e ACCESS_TOKEN_LIFE="30m" -e REFRESH_TOKEN_SECRET="mw_refresh_token_secret" -e REFRESH_TOKEN_LIFE="30d" s3975162/matchworks-server:latest
```

-   Linux

```bash
docker run -e CLIENT_URL='http://localhost:5173' \
  -e MONGO_URI='your-mongo-uri' \
  -e GEMINI_API_KEY='your-gemini-api-key' \
  -e ACCESS_TOKEN_SECRET='mw_access_token_secret' \
  -e ACCESS_TOKEN_LIFE='30m' \
  -e REFRESH_TOKEN_SECRET='mw_refresh_token_secret' \
  -e REFRESH_TOKEN_LIFE='30d' \
  s3975162/matchworks-server:latest

```

_replace `CLIENT_URL` with `http://localhost:4173` if client is running in deployment_
