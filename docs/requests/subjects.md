#### GET /subjects 

Returns a list of subjects. Supports:
 - pagination
 - searching by name
 - sorting by rating (DESC), name (ASC) and teacher count (DESC)

**Query:**
 - page
 - page_size
 - search
 - sort - `rating` (default), `name`, `teacherCount`

**Response:**
```js
{
    "count": $count,
    "items": [
        {
            "id": "$id",
            "link": "$link",
            "name": "$name",
            "teacher_count": $teacher_count,
            "rating": $rating
        },
        ...items
    ]
}
```

---

#### GET /subjects/*:link*

Returns information about the subject.

**Response:**
```js
{
    "id": "$id",
    "link": "$link",
    "name": "$name",
    "description": "$description",
    "teacher_count": $teacher_count,
    "rating": $rating
}
```

---

#### GET /subjects/*:link*/courses

Returns a list of courses. Supports:
 - pagination
 - searching by teacher's full name
 - sorting by rating (DESC) and lastName (ASC)

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
            "teacher": {
                "id": "$id",
                "first_name": "$first_name",
                "last_name": "$last_name",
                "middle_name": "$middle_name",
                "link": "$link"
            },
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
