# API Endpoints 

The following endpoints allow you to Get, Create & Delete your Playlists via the Music API.

## Returns the playlists - GET Playlists
Gets all the song playlists of a user.

##### **URL** 

```bash
GET https://api.muzicplayz.com/v3/playlist
```

##### **Query Parameters**

| Parameter | Description                                                                                      | Type    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `limit`   | Number of playlists to return                                                                    | integer |    No    |
| `offset`  | Index of the first playlist to return (e.g., `0` = start at beginning, `10` = skip first 10)     | integer |    No    |
| `search`  | Filter/Search for playlists matching a specific keyword or type of song                          | string  |    No    |

##### **Headers**

| Header Name | Description                                                                                      | Value    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `security`   | Basic Authorization                                                                           |          |    Yes    |

##### **Sample Request**

```bash
GET https://api.muzicplayz.com/v3/playlist?limit=10&offset=20&search=jazz 
  security: 
    - basauth: [] 
```

##### **Response**
- ###### Details of the playlist with songs.
###### `/components/schemas/playlistwithsongs`


| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `id`   | Id of the playlist  | integer |      |
| `name` | Name of the playlist | string |      |
| `songs`| Array of song details | array | [Check song details](#componentsschemassong)     | 


- ###### Details of related to the songs in the playlist.
###### `/components/schemas/song`

| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `id`   | Id of the song  | integer |       |
| `title` | Name of the song | string |      |
| `artist`| Name of the song | string |      | 

##### **Sample Response**
``` 
[
  {
    "id": 0,
    "name": "string",
    "songs": [
      {
        "id": 0,
        "title": "string",
        "artist": "string"
      }
    ]
  }
]
```

-----

-----

## Creates a playlist - POST Playlist
Creates a song playlist.

##### **URL** 

```bash
POST https://api.muzicplayz.com/v3/playlist
```

##### **Headers**

| Header Name | Description                                                                                      | Value    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `security`   | Basic Authorization                                                                           |          |    Yes    |


##### **Request Body**

- ###### Details of the new song playlist
###### `/components/schemas/newPlaylist`

| Element | Description                                                                                      | Type    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `name` | Name of the playlist | string | Yes     |
| `songIds`| Array of song Ids | array |    Yes    | 


##### **Sample Request**

``` bash
POST https://api.muzicplayz.com/v3/playlist
  security: 
    - basauth: []
  requestBody:
    required: true
    content:
      application/json:
      schema:
        $ref: "#/components/schemas/newPlaylist"
```

##### **Response**
- ###### Details of the playlist with songs.
###### `/components/schemas/playlistwithsongs`

| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `id`   | Id of the playlist  | integer |      |
| `name` | Name of the playlist | string |      |
| `songs`| Array of song details | array | [Check song details](#componentsschemassong)     |

- ###### Details of related to the songs in the playlist.
###### `/components/schemas/song`

| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `id`   | Id of the song  | integer |       |
| `title` | Name of the song | string |      |
| `artist`| Name of the song | string |      | 


##### **Sample Response**

```bash
{
  "id": 0,
  "name": "string",
  "songs": [
    {
      "id": 0,
      "title": "string",
      "artist": "string"
    }
  ]
}
```

-----

-----

## Returns a specific playlist - GET Specific Playlist
Gets a specific song playlist.

##### **URL** 

```bash
GET https://api.muzicplayz.com/v3/playlist/{playlist-id}
```

##### **Path Parameters**

| Parameter | Description                                                                                      | Type    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `playlist-id`   | Id of the playlist to return                                                         | integer |   Yes     |


##### **Headers**

| Header Name | Description                                                                                      | Value    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `security`   | Basic Authorization                                                                           |          |    Yes    |

##### **Sample Request**

```bash
GET https://api.muzicplayz.com/v3/playlist/{playlist-id}
  security:
    - basauth: []
  parameters:
    - name: playlist-id
      in: path
      required: true
      schema:
        type: string 
```

##### **Response**
- ###### Details of the playlist with songs.
###### `/components/schemas/playlistwithsongs`


| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `id`   | Id of the playlist  | integer |      |
| `name` | Name of the playlist | string |      |
| `songs`| Array of song details | array | [Check song details](#componentsschemassong)     | 


- ###### Details of related to the songs in the playlist.
###### `/components/schemas/song`

| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `id`   | Id of the song  | integer |       |
| `title` | Name of the song | string |      |
| `artist`| Name of the song | string |      | 

##### **Sample Response**
``` 
[
  {
    "id": 0,
    "name": "string",
    "songs": [
      {
        "id": 0,
        "title": "string",
        "artist": "string"
      }
    ]
  }
]
```

-----

-----

## Deletes a specific playlist - DELETE Specific Playlist
Deletes a specific song playlist.

##### **URL** 

```bash
DELETE https://api.muzicplayz.com/v3/playlist/{playlist-id}
```

##### **Path Parameters**

| Parameter | Description                                                                                      | Type    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `playlist-id`   | Id of the playlist to return                                                         | integer |   Yes     |


##### **Headers**

| Header Name | Description                                                                                      | Value    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `security`   | Basic Authorization                                                                           |          |    Yes    |

##### **Sample Request**

```bash
DELETE https://api.muzicplayz.com/v3/playlist/{playlist-id}
  security:
    - basauth: []
  parameters:
    - name: playlist-id
      in: path
      required: true
      schema:
        type: string 
```

##### **Response**
- ###### Details of the error message in response.
###### `/components/schemas/error`


| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `errormsg`   | Id of the playlist  | integer |      |
| `logdata` | Name of the playlist | string |  [Check logdata details](#componentsschemassong)     |

- ###### Details of logdata.

| Element | Description                                                                                      | Type    | Comments |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `entry`   | Id of the song  | integer |       |
| `date` | Name of the song | integer |      |

##### **Sample Response**
``` 
{
  "errormsg": "string",
  "logdata": {
    "entry": 0,
    "date": 0
  }
}
```

-----

-----

## Returns a specific playlist as Image - GET Specific Playlist as Image
Gets a specific song playlist as an image.

##### **URL** 

```bash
GET https://api.muzicplayz.com/v3/playlist/{playlist-id}/image
```

##### **Path Parameters**

| Parameter | Description                                                                                      | Type    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `playlist-id`   | Id of the playlist to return                                                         | integer |   Yes     |


##### **Headers**

| Header Name | Description                                                                                      | Value    | Required |
|-----------|--------------------------------------------------------------------------------------------------|---------|:--------:|
| `security`   | Basic Authorization                                                                           |          |    Yes    |

##### **Sample Request**

```bash
GET https://api.muzicplayz.com/v3/playlist/{playlist-id}/image
  security:
    - basauth: []
  parameters:
    - name: playlist-id
      in: path
      required: true
      schema:
        type: string 
```

##### **Sample Response**
``` 
string
```


