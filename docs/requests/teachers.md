
#### GET /teachers 

Returns a list of teachers. Supports:
 - pagination
 - searching by full name (concatenation of last name, first name and middle name) 
 - sorting by rating (DESC) and last name (ASC)

**Query:**
 - page
 - page_size
 - search
 - sort - `rating` (default), `lastName`

**Response:**
```js
{
    "count": $count,
    "items": [
        {
            "id": "$id",
            "link": "$link",
            "first_name": "$first_name",
            "middle_name": "$middle_name",
            "last_name": "$last_name",
            "rating": $rating
        },
        ...items
    ]
}
```

---

#### GET /teachers/*:link*

Returns a detailed information about the teacher.

**Response:**
```js
{
    "count": $count,
    "items": [
        {
            "id": "$id",
            "link": "$link",
            "first_name": "$first_name",
            "middle_name": "$middle_name",
            "last_name": "$last_name",
            "description": "$description",
            "image": "$image",
            "tags": ["$tag.0", "$tag.1", ...tags]
            "rating": $rating,
            "created_at": $created_at,
            "updated_at": $updated_at
        },
        ...items
    ]
}
```

---

#### GET /teachers/*:link*/courses

Returns a list of courses. Supports:
 - pagination
 - searching by name
 - sorting by rating (DESC) and name (ASC)

**Query:**
 - page
 - page_size
 - search
 - sort - `rating` (default), `name`

**Response:**
```js
{
    "count": $count,
    "items": [
        {
            "id": "$id",
            "link": "$link",
            "name": "$name",
            "review_count": $review_count,
            "rating": $rating,
            // whether this course is recommended by our editors
            // type: boolean
            "recommended": $recommended
        },
        ...items
    ]
}
```

---

#### GET /teachers/*:link*/contacts

Returns a list of contacts.

**Response:**
```js
{
    "items": [
        {
            "name": "$name",
            "value": "$value",
            "type": "$type"
        },
        ...items
    ]
}
```

---

#### GET /teachers/*:link*/reviews

Returns a list of reviews. Supports:
 - pagination
 - searching by course name
 - sorting by rating (DESC) and date (DESC)

**Query:**
 - page
 - page_size
 - search
 - sort - `rating`, `date` (default)

**Response:**
```js
{
    "count": $count,
    "items": [
        {
            "id": "$id",
            "content": "$content",
            "course": {
                "name": "$course.name",
                "link": "$course.link"
            },
            "rating": $rating,
            "date": $date
        },
        ...items
    ]
}
```

---

#### GET /teachers/*:link*/stats

Returns a list of stats from "ФИВТ им. Веры Петровны".

**Response:**
```js
{
    "items": [
        {
            "name": "$name",
            "value": $value
        },
        ...items
    ]
}
```
