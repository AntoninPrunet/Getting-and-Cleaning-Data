 Getting and Cleaning Data
 
The objective of this analysis is to work on a set of data in order to :

1- Merges the training and the test sets to create one data set.
2- Extracts only the measurements on the mean and standard deviation for each measurement.
3- Uses descriptive activity names to name the activities in the data set
4- Appropriately labels the data set with descriptive variable names.
5- From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

First, we uploaded all the files and packages.
Then, we loaded it into variables, using the function "fread".

Before merging the data between the training and test values, we created an index of all the variables including "mean" or "std" in their name (using the function "grep") and tidied up the names of these variables by removing the parentheses. Then, we merged x_train with x_test into x, by selecting only the variables containing "mean" or "std" (using the previously created index with the dyplr package select function, and the "cbind"/"rbind" functions for the merge).
Then, we used the activity_labels file in order to change the integers corresponding to the activity, into the character description of this activity.
Finally, before obtening the result, we melted the "activity" and "subject" in order to obtain the means of every other parameter in function of these two parameters, as requested (using "melt" and "decast" functions).