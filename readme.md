
---

##  1. Get Exam Marks

**Endpoint**
`GET /api/school/percentile/get_marks/<str:student_id>/`
> Replace `<student_id>` with exact Student_id

---

###  Description

Fetch exam marks of a student by student_id

---

---

###  Example Usage

```bash
# Get exam marks of a student
curl -X GET "http://localhost:8000/api/school/percentile/get_marks/123/"


```

---

###  Sample Success Response

```json
[
  {
    "student_id": "123",
    "session_id": "123",
    "student_class": "10",
    "marks": [
        {
            "subject": "grammar",
            "full_marks": 50,
            "exam1": 40,
            "exam2": 38,
            "exam3": 48
        },
        {
            "subject": "math",
            "full_marks": 100,
            "exam1": 78,
            "exam2": 85,
            "exam3": 92
        },
        {
            "subject": "science",
            "full_marks": 100,
            "exam1": 88,
            "exam2": 90,
            "exam3": 87
        }
    ],
    "updated_at": "2025-07-28T10:31:12.321594Z"
}
]
```



## 2. Submit Exam Marks

**Endpoint**
`POST /api/school/percentile/submit_marks/`

---

###  Description

Submit exam marks for a student based on student_id.
---

###  Request Body
```json
[
{
    "student_id": "123",
    "session_id": "123",
    "student_class": "10",
    "marks": [
        { "subject": "grammar", "full_marks": 50, "exam1": 40, "exam2": 38, "exam3": 48 },
        { "subject": "math", "full_marks": 100, "exam1": 78, "exam2": 85, "exam3": 92 },
        { "subject": "science", "full_marks": 100, "exam1": 88, "exam2": 90, "exam3": 87 }
    ]
}

]
```

---

###  Example Usage

```bash
curl -X POST "http://localhost:8000/api/school/percentile/submit_marks/" \
  -H "Content-Type: application/json" \
  -d '{
    "student_id": "123",
    "session_id": "123",
    "student_class": "10",
    "marks": [
        { "subject": "grammar", "full_marks": 50, "exam1": 40, "exam2": 38, "exam3": 48 },
        { "subject": "math", "full_marks": 100, "exam1": 78, "exam2": 85, "exam3": 92 },
        { "subject": "science", "full_marks": 100, "exam1": 88, "exam2": 90, "exam3": 87 }
    ]
}'
```

---

###  Sample Success Response

```json
{
    "message": "Mark submitted successfully",
    "data": {
        "student_id": "123",
        "session_id": "123",
        "student_class": "10",
        "marks": [
            {
                "subject": "grammar",
                "full_marks": 50,
                "exam1": 40,
                "exam2": 38,
                "exam3": 48
            },
            {
                "subject": "math",
                "full_marks": 100,
                "exam1": 78,
                "exam2": 85,
                "exam3": 92
            },
            {
                "subject": "science",
                "full_marks": 100,
                "exam1": 88,
                "exam2": 90,
                "exam3": 87
            }
        ],
        "updated_at": "2025-07-28T10:31:12.321594Z"
    }
}
```



