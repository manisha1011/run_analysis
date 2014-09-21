The "run_analysis.R" script follows the following steps:

- It loads the zipped data files from the (http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones) link and put it in a directory named "HAR" (if required, it will create the directory). Then unzips the zip file.

- Reads the features and filter only the features that contain "mean()" and "std()".

- Loads all train and test data but only the filtered features. It will use negative widths in "read.fwf" to skip the columns that are not required. That makes it much faster to load and process.

- Merges the subject files to main data and then merges all train, and test data (using rbind). The result is a dataframe named "all_data". It also labels the columns by the name of the features.

- Creates another dataframe named "all_average" that contains the mean of all columns by "subject". I have used "aggregate" function for that.

- Writes both dataframes into CSV files.
