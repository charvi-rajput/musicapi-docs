# Quickstart Guide

Get up and running with the Music API in minutes.

## Prerequisites

- Basic API Authorization
- HTTP client (like `curl`)

## Step 1: Create a Playlist

```bash
curl -X POST https://muzicplayz.com/v3/playlist \
  -d '{"name": "Chill Vibes", "songIds": [22, 3, 11, 45, 54]}'
```

## Step 2: Fetch Playlist as Image

```bash
curl -X GET https://muzicplayz.com/v3/playlist/{playlist-id}/image \
```

## Step 3: Fetch Playlists

```bash
curl -X GET https://muzicplayz.com/v3/playlists \
```

## Step 4: Fetch Specific Playlist

```bash
curl -X GET https://muzicplayz.com/v3/playlists/{playlist-id} \
```

## Step 5: Delete Playlist

```bash
curl -X DELETE https://muzicplayz.com/v3/playlists/{playlist-id} \
```