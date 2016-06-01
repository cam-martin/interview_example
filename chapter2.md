---
title       : Data Accumulation and Manipulation
description : Test your knowledge of statistical theory! Don't worry if you miss something we will give you the rundown on all you need to know
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:NormalExercise lang:r xp:100 skills:1 key:f5ed5290d0
## Data Manipulation
This exercise will test your ability to combine data from two different tables or data frames. This questions was taken from an interview submission by a Facebook employee on [Glassdoor.com](https://www.glassdoor.com/Interview/Facebook-Data-Scientist-Interview-Questions-EI_IE40772.0,8_KO9,23.htm).

`Table 1` has the following variables; `date`, `user_id`, `song_id`, `count`, where count is the total number of times a user has listened to a given song.

Table 2 has the same variables but instead of a lifetime total count, the count variable is the number of times a user has listened to a given song that particular day. This lifetime cumulative count needs to be updated daily.

The task is to pull the daily counts from the table 2 and add them to the cumulative count on table 1. 

Use any method you can think of to aggregate the daily counts with the cumulative counts. Your submission will be only judged based on the contents of the final table. Name your updated table `table_updated`.

If you get stuck, skip this exercise and go through one of the possible solutions in the following exercise. 

*** =instructions
- The task is to pull the daily counts from the `table 2` and add them to the cumulative count on `table 1`.
- We suggest you take a look at `table_1` and `table_2` they are already loaded in your environements
- Submit `table_updated` on its own line in the script.R 

*** =pre_exercise_code
```{r}
library(dplyr)
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_1_DM_FB.RData"))

load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_2_DM_FB.RData"))

load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_updated_DM_FB.RData"))


```
*** =sample_code
```{r}
# Explore the tables and submit your updated table here



```
*** =solution
```{r}
# The task is to pull the daily counts from the table 2 and add them to the cumulative count on table 1. 
table_updated
```
*** =sct
```{r}
test_data_frame("table_updated", columns = "count",
              incorrect_msg = "Your updated `count` variable is not working. Try again!")

# Final message the student will see upon completing the exercise
test_error()
success_msg("Good work! You were able to add the daily counts from table 2 to the total counts in table 1")
```
