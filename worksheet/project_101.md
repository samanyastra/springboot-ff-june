# Project101 - Student performance caluclator

## Description - Application to handle scores, performance and grade of students

- Application should be able to preload basic Student data as per below json data
```
[
    {
        name:"John Doe",
        class:12,
        batch:"2018",
        scores:{
            "Physics":45,
            "Biology":90,
            "Math":100,
            "Chemistry":87,
            "Computer Science":70
        }
    },
    {
        name:"John Blake",
        class:11,
        batch:"2018",
        scores:{
            "Physics":45,
            "Biology":90,
            "Math":100,
            "Chemistry":87,
            "Physical Education":70
        }
    },
    {
        name:"Joseph Marino",
        class:10,
        batch:"2018",
        scores:{
            "Physics":45,
            "Biology":90,
            "Math":100,
            "Chemistry":87,
            "Computer Science":70
        }
    },
    {
        name:"Jason Bourne",
        class:11,
        batch:"2019",
        scores:{
            "Physics":90,
            "Biology":70,
            "Math":60,
            "Chemistry":49,
            "Computer Science":91
        }
    }
]
```

### Note: Follow this grading system to calculate grades
    - Grading system
        - Grade 'A' - score btw 100(inclusive) and 90(exclusive)
        - Grade 'B' - score btw 90 and 80
        - Grade 'C' - score btw 80 and 70
        - Grade 'D' - score btw 70 and 60
        - Grade 'E' - score btw 60 and 50
        - Grade 'F' - for rest of them

### Create a function to show 
    - Percentage of each student(10)
    - Average of each class(10)
    - Overall school percentage Average(20)
    - Subject wise average score(30)
    - List all users with below details(30)
        - Name
        - class
        - Batch
        - Scores
            - Array of objects containing
                - Subject 
                - Score
                - Grade
