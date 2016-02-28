#Getting and Cleaning Data Course Project

#CookBook
Author: Antonio Bernal

Date: February 28, 2016

##Introduction
The scrip run_analysis.R performes the 5 steps described in the course project’s definition.

* The script downloads the .zip (compressed) file required for the analysis and extracts all the files from the compressed file.

* All files (x,y,subject) are merged using *rbind()* function. All files have the same number of observations( rows)

* Only the columns with the mean and standard deviation measurements are kept from the entire dataset. These variables are identified by using the *grep()* function. After extracting the variables of interest, these variables are renamed using the correct names from the *features.txt* file.

* Then activity values from 1 to 6 are substituted with the activities names from the *activity_labels.txt* file.

* A tidy dataset with the average measures for each subject and activity is generated. This dataset contains 180 observations( rows) [30 subjects times 6 activities]. The output data file is names activities)data.txt which is uploaded into this repository.

##Variables


* x_train, y_train and subject_train files include the train data and are extracted from the zip (compressed) file.

* x_test,y_test, and subject_test files include the test data and are extracted from the zip (compressed) file.

* x_data is created by merging the x_test and x_train data frames.  y_data is created by merging y_test and y_train. Similar process is used to create subject_data using subject_test and subject_train.

* The features data frame is used to apply the correct names to the variables in the x_data data frame. These correct names are used to create a numeric vector, *mean_and_std_features*,  which is used to extract the desired columns.

* activities, is a dataset created by reading the “activity_labels.txt’ file. this dataset contains two columns which represent the activity numbered activity name. 

* *all_data* is the resulting dataset after merging the x_data,y_data and subject_data datasets. This dataset contains 10,299 observations and 68 variables.
