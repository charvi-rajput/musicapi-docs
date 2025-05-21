# API Version History

This page documents all publicly released versions of the Music API.

---

## Version 1.0.0 – Initial Public Release  
**Release Date:** 2025-03-15  
**Status:** Stable  
**Version Type:** Major Release

### Summary

Version 1.0.0 marks the **first official release** of the Music API. This version includes all core playlist management features and introduces basic authentication.

### New Features

1. **Playlist Management Endpoints**  
`POST /playlist` : Create a new playlist  
`GET /playlist` : Fetch all playlists for the authenticated user  
`DELETE /playlist/{playlist_id}` : Delete a playlist by Id    

1. **Authentication**  
Basic Authentication via -
```bash
security:
  - basauth: []
```

1. **Rate Limiting/ Throttling**  
Number of Requests that this API can receive in a specific period are *none by default*.

### Technical Details

- API versioning is supported via the base path (`/v3`)
- JSON is the default request and response format
- All endpoints follow RESTful principles
- Error responses follow a unified schema :

```json
  {
    "errormsg": "This is an error msg"
  }
```

### Documentation & Tools
- Static documentation site available via MkDocs 
- Generated via Swagger/OpenAPI specifications


### Known Limitations
- No support for file uploads or media streaming yet
- Webhooks and SDKs are not yet available

### Versioning Policy
The Music API follows *Semantic Versioning :*

```bash
MAJOR: Incompatible API changes

MINOR: Backward-compatible feature additions

PATCH: Backward-compatible bug fixes
```

-----

-----

## Version 1.1.0 – New Features Release  
**Release Date:** 2025-04-26  
**Status:** Stable  
**Version Type:** Minor Release

### Summary

Version 1.1.0 marks the **new features release** of the Music API. This version includes some more playlist management features with basic authentication.

### New Features

1. **Playlist Management Endpoints**   
`GET /playlist/{playlist-id}` : Fetch a playlist by Id  
`GET /playlist/{playlist_id}/image` : Fetch a playlist by Id as image 

1. **Authentication**  
Basic Authentication via -
```bash
security:
  - basauth: []
```

1. **Rate Limiting/ Throttling**  
Number of Requests that this API can receive in a specific period are *none by default*.

### Technical Details

- API versioning is supported via the base path (`/v3`)
- JSON is the default request and response format
- All endpoints follow RESTful principles

### Documentation & Tools
- Static documentation site available via MkDocs 
- Generated via Swagger/OpenAPI specifications

### Known Limitations
- No support for file uploads or media streaming yet
- Webhooks and SDKs are not yet available

### Versioning Policy
The Music API follows *Semantic Versioning :*

```bash
MAJOR: Incompatible API changes

MINOR: Backward-compatible feature additions

PATCH: Backward-compatible bug fixes
```
Future versions will be listed below as they are released.