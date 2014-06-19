Getting_Cleaning_Data_Project
=============================

A repository with the R script used for performing the analysis, a CodeBook.md that describes the variables and a README.md file which explains how the script works.


## R Script
------------

"run_analysis.R" creates clean & tidy datasets out of the data collected from the accelerometers and gyroscopes from the Samsung Galaxy S smartphones. 

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

Link below for the raw / original data collected 
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 


### Actions Performed by the Script:

* Merges the training and the test sets to create one data set
* Extracts only the measurements on the mean and standard deviation for each measurement
* Uses descriptive activity names to name the activities in the data set & appropriately labels the data set with descriptive variable names
* Creates a second, independent tidy data set with the average of each variable for each activity and each volunteer


### Coding Steps:

* Loading raw data into R, assuming that all raw data files are located in the working directory
* Inspecting data & Its dimensions
* Combining data into one complete dataset with all variables
* Adding labels to variables / columns using the features vector
* Extracts only the measurements on the mean and standard deviation for each measurement (i.e. selecting features / columns containing the word "mean" or "std" using the "grep" function)
* Use activity_labels file to name the activities in the data set in a descriptive way, where currently we have a data set with activities as names, volunteers as IDs while selecting only the mean & standard deviation measurements 
* Arranging the dataset according to Volunteer ID & Activity type plus writing it to (.txt) file (clean_ordered_data.txt)


* Creating a 2nd , independent tidy data set with the average of each variable for each activity and each volunteer

	1. Creating a unique (Volunteer-Activity Identifier) for 	each variable by combining first two columns together
	2. Calculating the average for all variables per such 	Unique ID using "melt" & "cast" functions
	3. Currently we have for each volunteer and for each 	activity (unique ID) an average value for each variable
	4. Changing variables' / columns' names to reflect the 	average and writing it to a (.txt) file 	(average_ordered_data.txt)



R script last updated: 19th June 2014  ,  R version used: 3.0.3 (2014-03-06)

Definition & description of the various variables are included in the CodeBook.md file

### Reading Tidy Data Sets
-------------------------

Both data sets could be read using (read.table) functions while setting (header) value to (TRUE)



