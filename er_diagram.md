```mermaid
    erDiagram
    Quiz ||--|{ Question : has
    Quiz ||--|{ QuizDetails : has
    User ||--|{ Quiz : takes
    User ||--|{ Result : has
    Question ||--|{ AnswerSheet : has
    Quiz ||--|{ Result : has
    AnswerSheet ||--|{ User : submitted_by    

```
