---
title       : Data Accumulation and Manipulation
description : Test your knowledge of statistical theory! Don't worry if you miss something we will give you the rundown on all you need to know
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:NormalExercise lang:r xp:100 skills:1 key:f5ed5290d0
## Data Manipulation - Addind data from two tables

This exercise will test your ability to combine data from two different tables or data frames. This questions was taken from an interview submission by a prospective Facebook employee on [Glassdoor.com](https://www.glassdoor.com/Interview/Facebook-Data-Scientist-Interview-Questions-EI_IE40772.0,8_KO9,23.htm).

`Table 1` has the following variables; `date`, `user_id`, `song_id`, `count`, where count is the total number of times a user has listened to a given song.

`Table 2` has the same variables but instead of a lifetime total count, the count variable is the number of times a user has listened to a given song that particular day. This lifetime cumulative count needs to be updated daily.

The task is to pull the daily counts from the `table 2` and add them to the cumulative count on `table 1`. 

Use any method to aggregate the daily counts with the cumulative counts. Your submission will be only judged based on the contents of the final table. Name your updated table `table_updated`.

If you get stuck, skip this exercise and go through one of the possible solutions in the following exercise. 

*** =instructions
- The task is to pull the daily counts from the `table 2` and add them to the cumulative count on `table 1`.
- We suggest you take a look at `table_1` and `table_2` they are already loaded in your environements
- Submit `table_updated` on its own line in the script.R 
- 
*** =hint
- How can you combine the `count` variable without effecting the other variables?

*** =pre_exercise_code
```{r}
library(dplyr)
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_1_DM_FB.RData"))

load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_2_DM_FB.RData"))

#load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_updated_DM_FB.RData"))

```
*** =sample_code
```{r}
# Explore the tables and submit your updated table here



```
*** =solution
```{r}
# Explore the tables and submit your updated table here
table_updated <- table_1 %>% mutate(count = table_1$count + table_2$count)
```
*** =sct
```{r}
test_data_frame("table_updated", columns = "count",
              incorrect_msg = "Your updated `count` variable is not working. Try again!")

# Final message the student will see upon completing the exercise
test_error()
success_msg("Good work! You were able to add the daily counts from table 2 to the total counts in table 1")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:70b53164b2
## Data Manipulation Explaination - Addind data from two tables

The previous exercise tested your ability to combine data from two different tables or data frames. It was a very straight forward question and the solution could have been obtained in many ways. And each of those possible solutions has pros and cons.  

We will now run though a few possible solutions to this problem and see the differences in the approaches. 

The goal of the exercise was to combine the `count` from `table_2` with the `count` from `table_1`.

We can achive that in two ways
- simply adding `table_1` to `table_2`
- using a data manipulation package like `dplyr` and `mutating` the `count` variable. 

Run both of these approaches and see the differnces.

The `count` variable in both seem to be the same, but what happened to the other variables in the data frame? Although both approaches outputed the correct `count` variable can see which approach is the best.

In an interview, these details can demonstrate a more complete understanding of the language!

*** =instructions
- Add `table_1` with `table_2` using the `+` operator. Assign the output to `table_updated_1`.
- Using the package `dplyr`, `mutate` the `count` variable. Assign the output to `table_updated_2`.

*** =hint
- Remember to use the `%>%` operator when using a pipe. 

*** =pre_exercise_code
```{r}
library(dplyr)
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_1_DM_FB.RData"))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_1141/datasets/table_2_DM_FB.RData"))

```
*** =sample_code
```{r}
# Combine the two tables with the + operator
table_updated_1 <- _______ + ________

# Use dplyr to mutate the count variable
table_updated_2 <- table_1 ___ mutate(count = ______ + ______)

```
*** =solution
```{r}
# Combine the two tables with the + operator
table_updated_1 <- table_1 + table_2

# Use dplyr to mutate the count variable
table_updated_2 <- table_1 %>% mutate(count = table_1$count + table_2$count)

```
*** =sct
```{r}
test_data_frame("table_updated_1",
              incorrect_msg = "Your updated `count` variable is not working. Try again!")
              
test_data_frame("table_updated_2",
              incorrect_msg = "Your updated `count` variable is not working. Did you remember to isolate the `count` variables in each table with the `$` operator?")

test_function("mutate",
              incorrect_msg = "Your updated `count` variable is not working. Did you remember to isolate the `count` variables in each table with the `$` operator?")

# Final message the student will see upon completing the exercise
test_error()
success_msg("Good work! You were able to add the daily counts from table 2 to the total counts in table 1")
```

