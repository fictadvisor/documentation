#### GET /search

Seachy by query in subjects and teachers.
Response size should be limited to some constant amount (may be different for teachers and subjects)

**Query:**
 - query

**Response:**
```js
{
    "subjects": [
        {
            "id": "$id",
            "link": "$link",
            "name": "$name",
            "teacher_count": $teacher_count,
            "rating": $rating
        },
        ...subjects
    ],
    "teachers": [
        {
            "id": "$id",
            "link": "$link",
            "first_name": "$first_name",
            "middle_name": "$middle_name",
            "last_name": "$last_name",
            "rating": $rating
        },
        ...teachers
    ]
}
```