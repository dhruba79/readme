
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



## 2. Submit Feedback

**Endpoint**
`POST /api/school/submit_feedback/`

---

###  Description

Submit feedback responses for a student based on predefined questions.

---

###  Request Body
```json
[
{
  "user_id": "student123",
  "fid": "parent",
  "responses": [
    {
      "qid": "q1",
      "answer": [
        "mimicry_impersonation",
        "storytelling_expressiveness"
      ]
    },
    {
      "qid": "q6",
      "answer": "Yes"
    }
  ]
}
]
```

---

###  Example Usage

```bash
curl -X POST "http://localhost:8000/api/school/submit_feedback/" \
  -H "Content-Type: application/json" \
  -d '{
    "user_id": "student123",
    "fid": "parent",
    "responses": [
      {
        "qid": "q1",
        "answer": [
          "mimicry_impersonation",
          "storytelling_expressiveness"
        ]
      },
      {
        "qid": "q6",
        "answer": "Yes"
      }
    ]
  }'
```

---

###  Sample Success Response

```json
{
  "message": "Feedback submitted successfully"
}
```

---

Here’s a new section you can add to your `README.md` to document the API that retrieves submitted feedback for a user:

---

## 3. Retrieve Submitted Feedback

**Endpoint**
`GET /api/school/feedback/submission/<user_id>/<fid>/`

---

### 📋 Description

Fetch feedback submitted by a specific user (`user_id`) for a specific form type (`fid` - either `parent` or `teacher`).

---

###  Example Usage

```bash
# Get feedback submission of user "student32" for parent form
curl -X GET "http://localhost:8000/api/school/feedback/submission/student32/parent/"
```

---

###  Sample Success Response

```json
{
  "user_id": "student32",
  "fid": "parent",
  "responses": [
    {
      "qid": "q1",
      "answer": [
        "Quality 1",
        "Quality 2"
      ]
    },
    {
      "qid": "q6",
      "answer": "Yes"
    }
  ],
  "submitted_at": "2025-07-09T05:12:10.759982Z"
}
```

---




##  4. Get Leadership Trait Details

**Endpoint**
`GET /api/school/leadership-traits/<leadership_trait_name>/`

---

###  Description

Fetches all available details (qualities, hobbies, books, etc.) for a specific leadership trait such as `Actors`, `Writers`, etc.

---

###  Example Usage

```bash
# Get full details for the 'Actors' leadership trait
curl -X GET "http://localhost:8000/api/school/leadership-traits/Actors/"
```

---

###  Sample Success Response

```json
{
  "leadership_trait_name": "Actors",
  "unique_qualities": [
    "Mimicry Impersonation",
    "Storytelling Expressiveness",
    "Performance Skills Stage",
    "Observation Emotional Awareness"
  ],
  "hobbies": [
    "Sports Outdoor Activities",
    "Literature",
    "Performance Theatre Arts",
    "Observation Exploration"
  ],
  "books": [
    "An actor prepares",
    "Hamlet",
    "Plays from Shakespeare"
  ],
  "authors": [
    "Constantin Stanislavsky",
    "William Shakespeare",
    "Tennessee Williams"
  ],
  "communication_activities": [
    "Dramatics",
    "Debate",
    "Public Speaking"
  ],
  "public_service": [
    "Community Drives General Volunteering",
    "Charity",
    "Educational Camps",
    "Environmental Campaigns"
  ],
  "secondary_domain": [
    "Acting",
    "Writing",
    "Directing",
    "Film Making"
  ],
  "analytical_activities": [
    "Story Writing"
  ],
  "favourite_subjects": [
    "English",
    "History"
  ],
  "suggestions": [
    "Amir Khan",
    "Adam Douglas Driver",
    "Benjamin Geza Affleck",
    "William Bradley Pitt"
  ],
  "tips": [
    "Be sincere in your craft; Always strive to understand the character you are portraying;",
    "Stay patient. Stay persistent. Develop your craft. Make your mark",
    "Stay true to themselves. Work hard. Never give up",
    "Be patient; be persistent. Acting is a craft that needs time and effort to master. Always be open to learning. Always be open to evolving",
    "Be persistent; Stay true to themselves. Continuously learn and evolve. Portray characters authentically. Not lose yourself in the process."
  ]
}
```



## 5. Get All Leadership Traits

**Endpoint**
`GET /api/school/leadership-traits/`

---

###  Description

Returns a list of all available leadership traits with their detailed characteristics such as unique qualities, hobbies, books, authors, and more.

---

###  Example Usage

```bash
# Get a list of all leadership traits and their full details
curl -X GET "http://localhost:8000/api/school/leadership-traits/"
```

---

###  Sample Success Response

```json
[
  {
    "leadership_trait_name": "Actors",
    "unique_qualities": [
      "Mimicry Impersonation",
      "Storytelling Expressiveness",
      "Performance Skills Stage",
      "Observation Emotional Awareness"
    ],
    "hobbies": [
      "Sports Outdoor Activities",
      "Literature",
      "Performance Theatre Arts",
      "Observation Exploration"
    ],
    "books": [
      "An actor prepares",
      "Hamlet",
      "Plays from Shakespeare"
    ],
    "authors": [
      "Constantin Stanislavsky",
      "William Shakespeare",
      "Tennessee Williams"
    ],
    "communication_activities": [
      "Dramatics",
      "Debate",
      "Public Speaking"
    ],
    "public_service": [
      "Community Drives General Volunteering",
      "Charity",
      "Educational Camps",
      "Environmental Campaigns"
    ],
    "secondary_domain": [
      "Acting",
      "Writing",
      "Directing",
      "Film Making"
    ],
    "analytical_activities": [
      "Story Writing"
    ],
    "favourite_subjects": [
      "English",
      "History"
    ],
    "suggestions": [
      "Amir Khan",
      "Adam Douglas Driver",
      "Benjamin Geza Affleck",
      "William Bradley Pitt"
    ],
    "tips": [
      "Be sincere in your craft; Always strive to understand the character you are portraying;",
      "Stay patient. Stay persistent. Develop your craft. Make your mark",
      "Stay true to themselves. Work hard. Never give up",
      "Be patient; be persistent. Acting is a craft that needs time and effort to master. Always be open to learning. Always be open to evolving",
      "Be persistent; Stay true to themselves. Continuously learn and evolve. Portray characters authentically. Not lose yourself in the process."
    ]
  }
  // ...more traits
]
```

---



