
---

##  1. Get Feedback Questions

**Endpoint**
`GET /api/school/feedback_questions/<fid>/`
> Replace `<fid>` with either `parent` or `teacher`

---

###  Description

Fetch a list of feedback questions based on the role of the person providing the feedback.

---

---

###  Example Usage

```bash
# Get feedback questions for a parent
curl -X GET "http://localhost:8000/api/school/feedback_questions/parent/"

# Get feedback questions for a teacher
curl -X GET "http://localhost:8000/api/school/feedback_questions/teacher/"
```

---

###  Sample Success Response

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
      "imagination_creativity"
    ]
  },
  {
    "qid": "q6",
    "type": "radio",
    "label": "Has your kid participated any leadership activity?",
    "options": ["Yes", "No"]
  }
]
```

---

