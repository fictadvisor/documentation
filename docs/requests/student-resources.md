**GET** /student-resources `DONE`

Returns a list of student resources. Supports:
 - pagination
 - searching by name

**Query:**
 - page
 - page_size
 - search

**Response:**
```js
{
    "count": $count,
    "items": [
        {
            "id": "$id",
            "name": "$name",
            "url": "$url",
            "image": "$image"
        },
        ...items
    ]
}
```