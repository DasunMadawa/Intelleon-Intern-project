```mermaid

erDiagram
    USER {
        String username
        String name
        String password
        USER_ROLE role
        boolean isParticipated

    }

    QUIZ {
        String id
        Date startDateTime
        Date endDateTime
        String description
        int estimatedCount
        int participatedCount
        int noQuestions
        int technicalQCount
        int criticalQCount
        int otherQCount

    }

    QUESTION {
        String id
        String question
        String a
        String b
        String c
        String d
        String answer
        String type
        float totalAmount
        QUESTION_TYPE question_type
        int noQuiz
        int success
        int fail
        SEC section
        QUESTION_LEVEL question_level
        QUESTION_SECTION section

    }

    ANSWER_SHEET {
        String id
        Date submittedTime
        SUBMIT_TYPE submitType
        int successCount
        int failCount

    }

    ANSWER_SHEET_QUESTION {
        String answer
        boolean isCorrect

    }

    enum USER_ROLE {
        String ADMIN
        String CANDIDATE

    }

    enum QUESTION_TYPE {
        String MULTIPLE_ANSWERS
        String TRUE_FALSE
        String NORMAL

    }
    
    enum QUESTION_LEVEL {
        String EASY
        String MEDIUM
        String OTHER

    }
    
    enum QUESTION_SECTION {
        String TECHNICAL
        String CRITICAL
        String OTHER

    }


    enum SUBMIT_TYPE {
        String AUTO
        String MANUAL

    }


USER }o--o| QUIZ : join
QUIZ }o--|{ QUESTION : has
QUIZ ||--o{ ANSWER_SHEET : has
ANSWER_SHEET ||--|| USER : has
ANSWER_SHEET ||--o{ ANSWER_SHEET_QUESTION : has
ANSWER_SHEET_QUESTION }o--|| QUESTION : has
    

```
