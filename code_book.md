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

*The script also appropriately labels the data set with descriptive names: all feature names (attributes) and activity names are converted to lower case, underscores and brackets () are removed. Then both the data frames are merged together and the result is saved as merged_clean_data.txt, a which is a 10299 row and 68 coumn data frame such that the first column contains subject IDs, the second column activity names, and the last 66 columns are measurements. Subject IDs are integers between 1 and 30 inclusive. The names of the attributes are similar to the following:

>tbodyacc-mean-x 

>tbodyacc-mean-y 

>tbodyacc-mean-z 

>tbodyacc-std-x 

>tbodyacc-std-y 

>tbodyacc-std-z 

>tgravityacc-mean-x 

>tgravityacc-mean-y

* The script finally creates an independent tidy data set with the average of each measurement for each activity and each subject.
The result is saved as data_set_with_the_averages.txt, a data frame with 180 rows and 68 columns,where the first column contains subject IDs,the second column contains activity names,
and then the averages for each of the 66 attributes are in columns 3...68.
There are 30 subjects and 6 activities, thus 180 rows in this data set with averages.
