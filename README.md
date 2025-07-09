



````markdown
###  Feedback API Documentation:

This API provides endpoints to:
- Get feedback questions for parents and teachers.
- Submit feedback responses for students.

---
**
###  1. Feedback questions:

**Endpoint**:  
`GET /api/school/feedback_questions/<fid>/`  
Replace `<fid>` with either `parent` or `teacher`.

---

###  Examples

```bash
# Get feedback questions for parents
curl -X GET "http://localhost:8000/api/school/feedback_questions/parent/"

# Get feedback questions for teachers
curl -X GET "http://localhost:8000/api/school/feedback_questions/teacher/"
````

---

###  Sample Response:

```json
[
  {
    "qid": "q1",
    "type": "checkbox",
    "label": "Choose unique qualities from list of qualities",
    "options": [
      "mimicry_impersonation",
      "storytelling_expressiveness",
      "performance_skills_stage",
      "imagination_creativity",
      ...
    ]
  },
  ...
]
```

---

##  2. Submit Feedback

**Endpoint**:
`POST /api/school/submit_feedback`

---

###  Request Body:

```json
{
  "user_id": "student123",
  "fid": "parent",
  "responses": [
    {
      "qid": "q1",
      "answer": ["Quality 1", "Quality 2"]
    },
    {
      "qid": "q6",
      "answer": "Yes"
    }
  ]
}
```

---

###  Examples

```bash
# Submit feedback for parent
curl -X POST "http://localhost:8000/api/school/submit_feedback" \
  -H "Content-Type: application/json" \
  -d '{
        "user_id": "student123",
        "fid": "parent",
        "responses": [
          {
            "qid": "q1",
            "answer": ["mimicry_impersonation", "storytelling_expressiveness"]
          },
          {
            "qid": "q6",
            "answer": "Yes"
          }
        ]
      }'
```

---

###  Success Response:

```json
{
  "message": "Feedback submitted successfully"
}
```

---



```
```
