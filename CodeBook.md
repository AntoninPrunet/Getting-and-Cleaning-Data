<h1>Code Book</h1>


<h2>Project</h2>

This is the final [project](https://www.coursera.org/learn/data-cleaning/peer/FIZtT/getting-and-cleaning-data-course-project) for the Coursera module on "Getting and Cleaning Data", by John Hopkins University. The objective here is to :
<ul>
<li>Merges the training and the test sets to create one data set.</li>
<li>Extracts only the measurements on the mean and standard deviation for each measurement.</li>
<li>Uses descriptive activity names to name the activities in the data set</li>
<li>Appropriately labels the data set with descriptive variable names.</li>
<li>From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.</li>
</ul>

Information concerning the original data can be found on  [UCI website.](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones)

<h2>Getting and Cleaning Data</h2>
 
First, we upload all the files [here.](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
Then, we load it into variables, using the function `fread`. The chosen variable names in the [code](https://github.com/AntoninPrunet/Getting-and-Cleaning-Data/blob/master/run_analysis.R) are very similar to the names of the original files.

<h2>Explanation of the context</h2>

The variables are divided into two categories, the `_test` and the `_train`. They correspond to different situations where `subject` (ranked from 1 to 30 and distributed into `subject_test` and `subject_train`) perform activities (6 kinds described in `activity_labels`) during which many parameters (`features`) are measured. The objective is to manage to sort the data by `subject` and `activity` performed and measure the mean of the `features` that either correspond to a mean or a standard deviation.

<h2>Merging the data and tidying the variable names</h2>

Before merging the data between the training and test values, I created an `index` of all the variables including "mean" or "std" in their name (using the function `grep`) and tidied up the names of the features names by removing their parentheses (with `gsub`). Then, I merged `x_train` with `x_test` into `x`, by selecting only the variables containing "mean" or "std" (using the previously created index with the dyplr package select function, and the `cbind`/`rbind` functions for the merge).
Then, I used the `activity_labels` file in order to change the integers corresponding to the activity, into the character description of this activity.

<h2>Using melt and decast to get the means of the features</h2>

Finally, before obtening the result, I melted the `activity` and `subject` in order to obtain the means of every other parameter in function of these two parameters, as requested (using `melt` and `decast` functions).
The final file should create by itself in the repository with the code, and it should be named "tidydata.txt".

<h2>Links</h2>
Here is a link to my repository : [Repo](https://github.com/AntoninPrunet/Getting-and-Cleaning-Data).
<p></p>
Here is the link to my script : [script](https://github.com/AntoninPrunet/Getting-and-Cleaning-Data/blob/master/run_analysis.R).
<p></p>
And here is the link to the ReadMe page : [Read me](https://github.com/AntoninPrunet/Getting-and-Cleaning-Data/blob/master/README.md).

