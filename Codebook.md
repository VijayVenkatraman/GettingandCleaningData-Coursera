# Codebook
========================================================

This codebook describes the variables, the data, and any transformations or work that were performed to clean up the data. The codebook describes the data and variables from raw dataset and then the tidy dataset.
------------------------------------------------------------------------------------
## RAW DATASET
------------------------------------------------------------------------------------
The raw dataset for the project is explained in detail in ‘README.txt’ and ‘features_info.txt’ provided along with the dataset. Here is the brief information about the raw dataset: the experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years who performed six activities wearing a smartphone (Samsung Galaxy S II) on the waist. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers were selected for generating the training data and 30% the test data. The following data were used for creating the tidy dataset:

* Activity data (‘features.txt’; 'train/subject_train.txt'; 'train/subject_train.txt'):
* Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration (example: tAcc-XYZ and tGyro-XYZ).
* Triaxial Angular velocity from the gyroscope (example: tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ).
* A 561-feature vector with time and frequency domain variables. 
* Body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ).
* Euclidean norm were calculated (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).
* Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag.
* Activity labels ('activity_labels.txt'; 'train/y_train.txt' ; 'test/y_test.txt')
* Subject Identifier who carried out the experiment ('train/X_train.txt'; 'test/X_test.txt')

The major goal of the project was to create an independent tidy data set with the average of each variable for each activity and each subject. 

------------------------------------------------------------------------------------
## TIDY DATASET
------------------------------------------------------------------------------------
The raw dataset (text files) mentioned above were taken as inputs for generating the tidy dataset. Below is the summary of the steps or transformation on the dataset:
* Read the raw dataset 
* Rename the feature name according to acceptable format.
* Assign the feature names to the training and test raw dataset.
* Merge the dataset with subject IDs and activity labels for training and test dataset.
* Merge the training and test dataset into one and name the variables.
* Extract the mean and standard deviation measurements.
* Use the descriptive activity names instead of activity ID labels.
* Save the tidy dataset as “output_tidydataset.txt” 

## Variables:

There is a total of 68 variables and below groups that they belong: 
* Subject ID
* Activity Labels 
* Activity ID
* Body and gravity signals (time and frequency)
    * tbodyacc-XYZ
    * fbodyacc- XYZ
    * tbodygyro - XYZ
    * fbodygyro – XYZ
    * tgravityacc - XYZ
* Angular velocity (time and frequency)
    * tbodyaccjerk- XYZ
    * fbodyaccjerk- XYZ
    * tbodygyrojerk- XYZ
* Euclidean Norm (time and frequency) 
    * tbodyaccmag
    * tbodyaccjerkmag
    * tbodygyromag
    * tbodygyrojerkmag
    * tgravityaccmag
    * fbodyaccmag
    * fbodybodyaccjerkmag        
    * fbodybodygyromag     
    * fbodybodygyrojerkmag


## Dataset: names(data_goal5)
 [1] "activity"                  "subject"                   "activityID"               
 [4] "tbodyacc.mean.x"           "tbodyacc.mean.y"           "tbodyacc.mean.z"          
 [7] "tbodyacc.std.x"            "tbodyacc.std.y"            "tbodyacc.std.z"           
[10] "tgravityacc.mean.x"        "tgravityacc.mean.y"        "tgravityacc.mean.z"       
[13] "tgravityacc.std.x"         "tgravityacc.std.y"         "tgravityacc.std.z"        
[16] "tbodyaccjerk.mean.x"       "tbodyaccjerk.mean.y"       "tbodyaccjerk.mean.z"      
[19] "tbodyaccjerk.std.x"        "tbodyaccjerk.std.y"        "tbodyaccjerk.std.z"       
[22] "tbodygyro.mean.x"          "tbodygyro.mean.y"          "tbodygyro.mean.z"         
[25] "tbodygyro.std.x"           "tbodygyro.std.y"           "tbodygyro.std.z"          
[28] "tbodygyrojerk.mean.x"      "tbodygyrojerk.mean.y"      "tbodygyrojerk.mean.z"     
[31] "tbodygyrojerk.std.x"       "tbodygyrojerk.std.y"       "tbodygyrojerk.std.z"      
[34] "tbodyaccmag.mean"          "tbodyaccmag.std"           "tgravityaccmag.mean"      
[37] "tgravityaccmag.std"        "tbodyaccjerkmag.mean"      "tbodyaccjerkmag.std"      
[40] "tbodygyromag.mean"         "tbodygyromag.std"          "tbodygyrojerkmag.mean"    
[43] "tbodygyrojerkmag.std"      "fbodyacc.mean.x"           "fbodyacc.mean.y"          
[46] "fbodyacc.mean.z"           "fbodyacc.std.x"            "fbodyacc.std.y"           
[49] "fbodyacc.std.z"            "fbodyaccjerk.mean.x"       "fbodyaccjerk.mean.y"      
[52] "fbodyaccjerk.mean.z"       "fbodyaccjerk.std.x"        "fbodyaccjerk.std.y"       
[55] "fbodyaccjerk.std.z"        "fbodygyro.mean.x"          "fbodygyro.mean.y"         
[58] "fbodygyro.mean.z"          "fbodygyro.std.x"           "fbodygyro.std.y"          
[61] "fbodygyro.std.z"           "fbodyaccmag.mean"          "fbodyaccmag.std"          
[64] "fbodybodyaccjerkmag.mean"  "fbodybodyaccjerkmag.std"   "fbodybodygyromag.mean"    
[67] "fbodybodygyromag.std"      "fbodybodygyrojerkmag.mean" "fbodybodygyrojerkmag.std"


## Summary of variables:
> summary(data_goal5)
               activity     subject       activityID  tbodyacc.mean.x  tbodyacc.mean.y    
 WALKING           :30   Min.   : 1.0   Min.   :1.0   Min.   :0.2216   Min.   :-0.040514  
 WALKING_UPSTAIRS  :30   1st Qu.: 8.0   1st Qu.:2.0   1st Qu.:0.2712   1st Qu.:-0.020022  
 WALKING_DOWNSTAIRS:30   Median :15.5   Median :3.5   Median :0.2770   Median :-0.017262  
 SITTING           :30   Mean   :15.5   Mean   :3.5   Mean   :0.2743   Mean   :-0.017876  
 STANDING          :30   3rd Qu.:23.0   3rd Qu.:5.0   3rd Qu.:0.2800   3rd Qu.:-0.014936  
 LAYING            :30   Max.   :30.0   Max.   :6.0   Max.   :0.3015   Max.   :-0.001308  
 tbodyacc.mean.z    tbodyacc.std.x    tbodyacc.std.y     tbodyacc.std.z    tgravityacc.mean.x
 Min.   :-0.15251   Min.   :-0.9961   Min.   :-0.99024   Min.   :-0.9877   Min.   :-0.6800   
 1st Qu.:-0.11207   1st Qu.:-0.9799   1st Qu.:-0.94205   1st Qu.:-0.9498   1st Qu.: 0.8376   
 Median :-0.10819   Median :-0.7526   Median :-0.50897   Median :-0.6518   Median : 0.9208   
 Mean   :-0.10916   Mean   :-0.5577   Mean   :-0.46046   Mean   :-0.5756   Mean   : 0.6975   
 3rd Qu.:-0.10443   3rd Qu.:-0.1984   3rd Qu.:-0.03077   3rd Qu.:-0.2306   3rd Qu.: 0.9425   
 Max.   :-0.07538   Max.   : 0.6269   Max.   : 0.61694   Max.   : 0.6090   Max.   : 0.9745   
 tgravityacc.mean.y tgravityacc.mean.z tgravityacc.std.x tgravityacc.std.y tgravityacc.std.z
 Min.   :-0.47989   Min.   :-0.49509   Min.   :-0.9968   Min.   :-0.9942   Min.   :-0.9910  
 1st Qu.:-0.23319   1st Qu.:-0.11726   1st Qu.:-0.9825   1st Qu.:-0.9711   1st Qu.:-0.9605  
 Median :-0.12782   Median : 0.02384   Median :-0.9695   Median :-0.9590   Median :-0.9450  
 Mean   :-0.01621   Mean   : 0.07413   Mean   :-0.9638   Mean   :-0.9524   Mean   :-0.9364  
 3rd Qu.: 0.08773   3rd Qu.: 0.14946   3rd Qu.:-0.9509   3rd Qu.:-0.9370   3rd Qu.:-0.9180  
 Max.   : 0.95659   Max.   : 0.95787   Max.   :-0.8296   Max.   :-0.6436   Max.   :-0.6102  
 tbodyaccjerk.mean.x tbodyaccjerk.mean.y  tbodyaccjerk.mean.z tbodyaccjerk.std.x tbodyaccjerk.std.y
 Min.   :0.04269     Min.   :-0.0386872   Min.   :-0.067458   Min.   :-0.9946    Min.   :-0.9895   
 1st Qu.:0.07396     1st Qu.: 0.0004664   1st Qu.:-0.010601   1st Qu.:-0.9832    1st Qu.:-0.9724   
 Median :0.07640     Median : 0.0094698   Median :-0.003861   Median :-0.8104    Median :-0.7756   
 Mean   :0.07947     Mean   : 0.0075652   Mean   :-0.004953   Mean   :-0.5949    Mean   :-0.5654   
 3rd Qu.:0.08330     3rd Qu.: 0.0134008   3rd Qu.: 0.001958   3rd Qu.:-0.2233    3rd Qu.:-0.1483   
 Max.   :0.13019     Max.   : 0.0568186   Max.   : 0.038053   Max.   : 0.5443    Max.   : 0.3553   
 tbodyaccjerk.std.z tbodygyro.mean.x   tbodygyro.mean.y   tbodygyro.mean.z   tbodygyro.std.x  
 Min.   :-0.99329   Min.   :-0.20578   Min.   :-0.20421   Min.   :-0.07245   Min.   :-0.9943  
 1st Qu.:-0.98266   1st Qu.:-0.04712   1st Qu.:-0.08955   1st Qu.: 0.07475   1st Qu.:-0.9735  
 Median :-0.88366   Median :-0.02871   Median :-0.07318   Median : 0.08512   Median :-0.7890  
 Mean   :-0.73596   Mean   :-0.03244   Mean   :-0.07426   Mean   : 0.08744   Mean   :-0.6916  
 3rd Qu.:-0.51212   3rd Qu.:-0.01676   3rd Qu.:-0.06113   3rd Qu.: 0.10177   3rd Qu.:-0.4414  
 Max.   : 0.03102   Max.   : 0.19270   Max.   : 0.02747   Max.   : 0.17910   Max.   : 0.2677  
 tbodygyro.std.y   tbodygyro.std.z   tbodygyrojerk.mean.x tbodygyrojerk.mean.y tbodygyrojerk.mean.z
 Min.   :-0.9942   Min.   :-0.9855   Min.   :-0.15721     Min.   :-0.07681     Min.   :-0.092500   
 1st Qu.:-0.9629   1st Qu.:-0.9609   1st Qu.:-0.10322     1st Qu.:-0.04552     1st Qu.:-0.061725   
 Median :-0.8017   Median :-0.8010   Median :-0.09868     Median :-0.04112     Median :-0.053430   
 Mean   :-0.6533   Mean   :-0.6164   Mean   :-0.09606     Mean   :-0.04269     Mean   :-0.054802   
 3rd Qu.:-0.4196   3rd Qu.:-0.3106   3rd Qu.:-0.09110     3rd Qu.:-0.03842     3rd Qu.:-0.048985   
 Max.   : 0.4765   Max.   : 0.5649   Max.   :-0.02209     Max.   :-0.01320     Max.   :-0.006941   
 tbodygyrojerk.std.x tbodygyrojerk.std.y tbodygyrojerk.std.z tbodyaccmag.mean  tbodyaccmag.std  
 Min.   :-0.9965     Min.   :-0.9971     Min.   :-0.9954     Min.   :-0.9865   Min.   :-0.9865  
 1st Qu.:-0.9800     1st Qu.:-0.9832     1st Qu.:-0.9848     1st Qu.:-0.9573   1st Qu.:-0.9430  
 Median :-0.8396     Median :-0.8942     Median :-0.8610     Median :-0.4829   Median :-0.6074  
 Mean   :-0.7036     Mean   :-0.7636     Mean   :-0.7096     Mean   :-0.4973   Mean   :-0.5439  
 3rd Qu.:-0.4629     3rd Qu.:-0.5861     3rd Qu.:-0.4741     3rd Qu.:-0.0919   3rd Qu.:-0.2090  
 Max.   : 0.1791     Max.   : 0.2959     Max.   : 0.1932     Max.   : 0.6446   Max.   : 0.4284  
 tgravityaccmag.mean tgravityaccmag.std tbodyaccjerkmag.mean tbodyaccjerkmag.std tbodygyromag.mean
 Min.   :-0.9865     Min.   :-0.9865    Min.   :-0.9928      Min.   :-0.9946     Min.   :-0.9807  
 1st Qu.:-0.9573     1st Qu.:-0.9430    1st Qu.:-0.9807      1st Qu.:-0.9765     1st Qu.:-0.9461  
 Median :-0.4829     Median :-0.6074    Median :-0.8168      Median :-0.8014     Median :-0.6551  
 Mean   :-0.4973     Mean   :-0.5439    Mean   :-0.6079      Mean   :-0.5842     Mean   :-0.5652  
 3rd Qu.:-0.0919     3rd Qu.:-0.2090    3rd Qu.:-0.2456      3rd Qu.:-0.2173     3rd Qu.:-0.2159  
 Max.   : 0.6446     Max.   : 0.4284    Max.   : 0.4345      Max.   : 0.4506     Max.   : 0.4180  
 tbodygyromag.std  tbodygyrojerkmag.mean tbodygyrojerkmag.std fbodyacc.mean.x   fbodyacc.mean.y   
 Min.   :-0.9814   Min.   :-0.99732      Min.   :-0.9977      Min.   :-0.9952   Min.   :-0.98903  
 1st Qu.:-0.9476   1st Qu.:-0.98515      1st Qu.:-0.9805      1st Qu.:-0.9787   1st Qu.:-0.95361  
 Median :-0.7420   Median :-0.86479      Median :-0.8809      Median :-0.7691   Median :-0.59498  
 Mean   :-0.6304   Mean   :-0.73637      Mean   :-0.7550      Mean   :-0.5758   Mean   :-0.48873  
 3rd Qu.:-0.3602   3rd Qu.:-0.51186      3rd Qu.:-0.5767      3rd Qu.:-0.2174   3rd Qu.:-0.06341  
 Max.   : 0.3000   Max.   : 0.08758      Max.   : 0.2502      Max.   : 0.5370   Max.   : 0.52419  
 fbodyacc.mean.z   fbodyacc.std.x    fbodyacc.std.y     fbodyacc.std.z    fbodyaccjerk.mean.x
 Min.   :-0.9895   Min.   :-0.9966   Min.   :-0.99068   Min.   :-0.9872   Min.   :-0.9946    
 1st Qu.:-0.9619   1st Qu.:-0.9820   1st Qu.:-0.94042   1st Qu.:-0.9459   1st Qu.:-0.9828    
 Median :-0.7236   Median :-0.7470   Median :-0.51338   Median :-0.6441   Median :-0.8126    
 Mean   :-0.6297   Mean   :-0.5522   Mean   :-0.48148   Mean   :-0.5824   Mean   :-0.6139    
 3rd Qu.:-0.3183   3rd Qu.:-0.1966   3rd Qu.:-0.07913   3rd Qu.:-0.2655   3rd Qu.:-0.2820    
 Max.   : 0.2807   Max.   : 0.6585   Max.   : 0.56019   Max.   : 0.6871   Max.   : 0.4743    
 fbodyaccjerk.mean.y fbodyaccjerk.mean.z fbodyaccjerk.std.x fbodyaccjerk.std.y fbodyaccjerk.std.z 
 Min.   :-0.9894     Min.   :-0.9920     Min.   :-0.9951    Min.   :-0.9905    Min.   :-0.993108  
 1st Qu.:-0.9725     1st Qu.:-0.9796     1st Qu.:-0.9847    1st Qu.:-0.9737    1st Qu.:-0.983747  
 Median :-0.7817     Median :-0.8707     Median :-0.8254    Median :-0.7852    Median :-0.895121  
 Mean   :-0.5882     Mean   :-0.7144     Mean   :-0.6121    Mean   :-0.5707    Mean   :-0.756489  
 3rd Qu.:-0.1963     3rd Qu.:-0.4697     3rd Qu.:-0.2475    3rd Qu.:-0.1685    3rd Qu.:-0.543787  
 Max.   : 0.2767     Max.   : 0.1578     Max.   : 0.4768    Max.   : 0.3498    Max.   :-0.006236  
 fbodygyro.mean.x  fbodygyro.mean.y  fbodygyro.mean.z  fbodygyro.std.x   fbodygyro.std.y  
 Min.   :-0.9931   Min.   :-0.9940   Min.   :-0.9860   Min.   :-0.9947   Min.   :-0.9944  
 1st Qu.:-0.9697   1st Qu.:-0.9700   1st Qu.:-0.9624   1st Qu.:-0.9750   1st Qu.:-0.9602  
 Median :-0.7300   Median :-0.8141   Median :-0.7909   Median :-0.8086   Median :-0.7964  
 Mean   :-0.6367   Mean   :-0.6767   Mean   :-0.6044   Mean   :-0.7110   Mean   :-0.6454  
 3rd Qu.:-0.3387   3rd Qu.:-0.4458   3rd Qu.:-0.2635   3rd Qu.:-0.4813   3rd Qu.:-0.4154  
 Max.   : 0.4750   Max.   : 0.3288   Max.   : 0.4924   Max.   : 0.1966   Max.   : 0.6462  
 fbodygyro.std.z   fbodyaccmag.mean  fbodyaccmag.std   fbodybodyaccjerkmag.mean
 Min.   :-0.9867   Min.   :-0.9868   Min.   :-0.9876   Min.   :-0.9940         
 1st Qu.:-0.9643   1st Qu.:-0.9560   1st Qu.:-0.9452   1st Qu.:-0.9770         
 Median :-0.8224   Median :-0.6703   Median :-0.6513   Median :-0.7940         
 Mean   :-0.6577   Mean   :-0.5365   Mean   :-0.6210   Mean   :-0.5756         
 3rd Qu.:-0.3916   3rd Qu.:-0.1622   3rd Qu.:-0.3654   3rd Qu.:-0.1872         
 Max.   : 0.5225   Max.   : 0.5866   Max.   : 0.1787   Max.   : 0.5384         
 fbodybodyaccjerkmag.std fbodybodygyromag.mean fbodybodygyromag.std fbodybodygyrojerkmag.mean
 Min.   :-0.9944         Min.   :-0.9865       Min.   :-0.9815      Min.   :-0.9976          
 1st Qu.:-0.9752         1st Qu.:-0.9616       1st Qu.:-0.9488      1st Qu.:-0.9813          
 Median :-0.8126         Median :-0.7657       Median :-0.7727      Median :-0.8779          
 Mean   :-0.5992         Mean   :-0.6671       Mean   :-0.6723      Mean   :-0.7564          
 3rd Qu.:-0.2668         3rd Qu.:-0.4087       3rd Qu.:-0.4277      3rd Qu.:-0.5831          
 Max.   : 0.3163         Max.   : 0.2040       Max.   : 0.2367      Max.   : 0.1466          
 fbodybodygyrojerkmag.std
 Min.   :-0.9976         
 1st Qu.:-0.9802         
 Median :-0.8941         
 Mean   :-0.7715         
 3rd Qu.:-0.6081         
 Max.   : 0.2878

