---
title       : Data Accumulation and Manipulation
description : Test your knowledge of statistical theory! Don't worry if you miss something we will give you the rundown on all you need to know
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:NormalExercise lang:r xp:100 skills:1 key:f5ed5290d0
## Data Manipulation

Table 1 has the following variables:
- date
- user_id
- song_id
- count 
where count is the total number of times a user has listened to a given song.

Table 2 has the same variables but instead of a lifetime total count, the count variable is the number of times a user has listened to a given song that particular day.

This lifetime cumulative count needs to be updated daily.

The task is to pull the daily counts from the table 2 and add them to the cumulative count on table 1. 

Use any method you can think of to aggregate the daily counts with the cumulative counts. Your submission will be only judged based on the contents of the final table. Name your updated table `table_updated`.

If you get stuck, skip this exercise and go through one of the possible solutions in the following exercise. 

*** =pre_exercise_code
```{r}
library(dplry)
load(url("s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_1_DM_FB.RData"))
table_1 <- table_1_DM_FB
load(url("s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_2_DM_FB.RData"))
table_2 <- table_2_DM_FB
load(url("s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_updated_DM_FB.RData"))
table_updated <- table_updated_DM_FB

```
*** =sample_code
```{r}
# The task is to pull the daily counts from the table 2 and add them to the cumulative count on table 1. 
# We suggest you take a look at `table_1` and `table_2` they are already loaded in your environements

```
*** =solution
```{r}
# The task is to pull the daily counts from the table 2 and add them to the cumulative count on table 1. 
table_updated
```
*** =sct
```{r}
test_data_frame("table_updated",
              incorrect_msg = "Did you remember to define the object `Lets_go`? Just remove the `#`.")

# Final message the student will see upon completing the exercise
test_error()
success_msg("Good work! You were able to add the daily counts from table 2 to the total counts in table 1")
```
