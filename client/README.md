# MatchWorks Client

Document: <a href="https://matchworks-client-storybook.k-clowd.top/" target="_blank">Storybook</a>

## Installation

1. Install

```bash
npm i
```

2. Run

```bash
npm run dev
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
npx vite preview --host 0.0.0.0
```

### Docker

1. Build

```bash
docker-compose build --build-arg VITE_SERVER_URL="http://localhost:8080"
```

2. Run

```bash
docker-compose up
```
