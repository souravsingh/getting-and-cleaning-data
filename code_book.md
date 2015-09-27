# Code Book for the Course Project

Source of the original data: https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

Original description: http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

The attached R script (run_analysis.R) performs the following to clean up the data:

* Merges the training and test sets to create one data set, namely train/X_train.txt with test/X_test.txt,
train/subject_train.txt with test/subject_test.txt, the result of which is a data frame with subject IDs,
and train/y_train.txt with test/y_test.txt,the result of which is also a 10299x1 data frame with activity IDs.

* Reads features.txt and extracts the measurements on the mean and standard deviation for each measurement.
The result is a data frame,containing mean and standard deviation on each measurement.
All measurements appear to be floating point numbers in the range (-1, 1).

* Reads activity_labels.txt and applies activity names to name the activities in the data set:

>walking

>walkingupstairs

>walkingdownstairs

>sitting

>standing

>laying

The script finally creates an independent tidy data set with the average of each measurement for each activity and each subject.
The result is saved as data_set_with_the_averages.txt, a data frame,where the first column contains subject IDs,the second column contains activity names,
and then the averages for each of the 66 attributes are in columns 3...68.
There are 30 subjects and 6 activities, thus 180 rows in this data set with averages.
