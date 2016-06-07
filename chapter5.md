---
title       : Critical thinking
description : One of the most importants skills of a data scientist is the ability to think critically. Here are a series of mind benders to get you thinking critically. The challenge is not the coding, but thinking through the complex problems. We will provided detail interactive feedback for each mind game to really sharpen your critical thinking abilities.  
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf


--- type:MultipleChoiceExercise xp:50 skills:1  key:f48b5ed8a3
## Colored Snakes Brain Game

Brain Games are a great way for interviewers to get a sence of how your mind works. They make you think in different ways and challenge you to think outside the box. 

You will be given a number of challenges and riddles to try to solve. In your interview you may not have R to use as a giant calculator but solving these puzzels here will be great practice. It can even help you visualize how you would solve the problem and that is what the interviewers are most interested in learning about you. 

Use the R script to make any calculations but you will be only judged on your final solution. 

Let's get right to it. No holding back. 

In this senario, there are 13 blue, 15 red, and 17 yellow snakes. Everytime two opposing colored snakes meet their color switches to the third color. A red snake meets a blue snake and they both turn yellow. 

The question is, could the snakes meet so that eventually all snakes become the same color?

*** =instructions
- Yes, you can achieve a monochormatic band of snakes!
- No, you will always have at least two colors.
*** =hint
Try simplifying the numbers, can you get all one color with just 1 blue, 3 red and 7 yellow?   

*** =pre_exercise_code
```{r,eval=FALSE}
```

*** =sct
```{r,eval=FALSE}
msg1 <- "Are you sure? Let's take another look in the next exercise."
msg2 <- "Nice work! It is impossible no matter what combinations you try."
test_mc(correct = 2, feedback_msgs = c(msg1, msg2))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:f5ed5290d0
## Colored Snakes Brain Game

In the previous exercise, you had to decide whether you could combine 3 groups of colored snakes to make a gourp with just one color knowing that when two different colored snakes met they changed to the third color.

This seems like an easy task but when if you tried to manually combine snakes you realized that your mind has a hard time being confident that there is not solution. 

The following code demonstrates that there is a way to be sure that you are right! Here is one way to justify that it is impossible to combine pairs of snakes to get all the snakes to be just one color. 

*** =instructions
- Follow the code detailing a possible solution to the brain game

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# Make a quik data frame with the infromation about the snakes
color <- ___________
count <- c(__,__,__)
snakes <- data.frame(color,count)
```

*** =solution
```{r}
color <- c("blue_snakes","red_snakes","yellow_snakes")
count <- c(13,15,17)
snakes <- data.frame(color,count)
```

*** =sct
```{r}
test_data_frame("snakes",
              incorrect_msg = "Did you remember to define the object `Lets_go`? Just remove the `#`.")

test_function("print", args = "x",
              not_called_msg = "You use the `print()` function",
              args_not_specified_msg = "Something went wrong with your `print()` fucntion. Did you remember to remove both `#s`",
              incorrect_msg = "Something went wrong with your `print()` fucntion. Did you remember to remove both `#s`")


# Final message the student will see upon completing the exercise
test_error()
success_msg("Good work!")
```

--- type:NormalExercise lang:r xp:100 skills:1 key:c6a787c38c
## Falling eggs Brain Game

You have two identical eggs. Standing in front of a 100 floor building, you wonder what is the maximum number of floors from which the egg can be dropped without breaking it. What is the minimum number of tries needed to find out the solution?

*** =instructions
- Make any calculations in the R script to solve the brain game.
- Assign your final and answer as `final_answer`. This is the only value that will be judged in this exercise. 

*** =pre_exercise_code
```{r}

```

*** =sample_code
```{r}
# What is the minimum number of tries needed to find out the solution?
final_answer <-

```

*** =solution
```{r}
# What is the minimum number of tries needed to find out the solution?
final_answer <- 19
```

*** =sct
```{r}
test_objecct("final_answer",
              incorrect_msg = "Not quite. If you can't find the answer, click hint and then solution. We will go through the answer in the next exercise!")

# Final message the student will see upon completing the exercise
test_error()
success_msg("Great work! Now let's see how we arrived at that answer.")
```


