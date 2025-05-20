#  API Authentication

All Music API endpoints require a basic authorization in the `security` header.

## Request 

```
/playlist:
  get:
    Host: (https://api.muzicplayz.com/v3)  
    security:
      - basauth: []
```
