---
title       : Interview Prep Course Example
description : Test and sharpen your data science interview skills
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:NormalExercise lang:r xp:100 skills:1 key:f5ed5290d0
## Intro to Interview Prep

In this course/tutorial you will test your data science expertice by answering common interview questions. 

First, you will be presented by a question or senario that would commonly be in a data science interview. You will be given little help at first, these tutorials are designed to test your knowledge so that you can gave what ares you need to brush up on before your interview!

After we test your understanding and technical ability, we will walk you through each solution to make sure that you fully understand the elements of the interview question.

In between each exercise are multiple choice about the theoretical practice of data science. These will require less interactive coding to solve, but are useful to keep your data science theory sharp. 

This course will cover 5 general topics that all data sciencists should have mastered:
- 
-
-
-
-

Lets begin!

Run the sample code to move to the first exercise.
*** =instructions
- Remove the `#s` to move on to the first exercise.
- 
*** =hint
- Don't change any of the sample code, just remove the `#`. 

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Are you ready to see what you know?
#Lets_go <- Yes!
#print(Lets_go)
```

*** =solution
```{r}
# Are you ready to see what you know?
Lets_go <- Yes!
print(Lets_go)
```

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package. Documentation can also be found at github.com/datacamp/testwhat/wiki

# Test whether the function str is called with the correct argument, object
# If it is not called, print something informative
# If it is called, but called incorrectly, print something else
test_function("print", args = "object",
              not_called_msg = "You use the `print()` function",
              incorrect_msg = "Something went wrong with your `print()` fucntion. Did you remember to remove both `#s`")

# Final message the student will see upon completing the exercise
test_error()
success_msg("Good work!")
```