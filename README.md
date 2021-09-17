# pump_it_up_competition

Repo link: https://github.com/DARathnasiri/pump_it_up_competition

##
1) Required packages are imported.
2) Train values and test values are imported to pandas dataframes.
3) Create a combined pandas dataframe of train values and test values.

## Explotary data analysis
4) Plot graphs for each feature for explotary data analysis using seaborn.

## Handling Outliers
5) amount_tsh, construction_year, longitude features has outliers.
6) 0 outlier values in construction_year features replace with mean of the non zero values of construction_year.
7) 0 outlier values in longitude features replace with mean of the non zero values of longitude.

## Modify features
8) id feature is a unique value to each row.
9) Therefore id is not useful for predictions.
10) Therefore id feature is dropped.
11) num_private feature is not a useful value for predictions.
12) Therefore num_private feature is dropped.
13) The recorded_by column has only one value.
14) Therefore it is not useful for predictions.
15) Therefore recorded_by feature is dropped.
16) Installer feature has 0 values. They are unknown values.
17) Therefore 0 values replaced with 'missing' value in installer.
18) Installer feature has missing values.
19) Missing values in installer feature are filled with 'missing' value.
21) Replace the spelling mistakes and collect same categories in same name in installer feature.
22) Installer values which has less than 400 value counts collect together and named them 'others'.
23) Funder feature has 0 values. They are unknown values.
24) Therefore 0 values replaced with 'missing' value in funder.
25) Funder feature has missing values.
26) Missing values in funder feature are filled with 'missing' value.
27) Funder values which has less value counts collect together and named them 'others'.

## Feature scaling
28) Float and integer features are scaled using standard scaler.
29) Standard scaler produce more accuracy in prediction than the min max scaler.
30) scale amount_tsh, latitude, longitude, gps_height, population features are scaled using standard scaler.

## Encode features
31) All object features (not ineger and float) are label encoded.

## Filling missing values
32) scheme_name, scheme_management, public_meeting, permit, subvillage features still have missing values.
33) Since 0.4749 of scheme_name values are missing, scheme_name column is dropped.
34) Analyse correlation of the scheme_management column with other columns.
35) scheme_management has high correlation with management_group.

management_group      highest frequncy scheme_management value
0                         6
1                         1
2                         8
3                         0
4                         0

36) Missing vales of scheme_management are filled with values that has highest frequency in each management_group shown in the above table.
37) Analyse correlation of the public_meeting column with other features.
38) public_meeting has high correlation with management_group.

management_group          highest frequncy public_meeting value
0                              0
1                              0
2                              0
3                              0
4                              0

39) Missing values of public_meeting are filled with values that has highest frequency in each management_group shown in the above table.
40) Consider missing values in permit as a seperate class and do the label encoding.
41) Consider missing values in subvillage as a seperate class and do the label encoding.

##

42) Divide combined pandas dataframe to train pandas dataframe and test pandas dataframe.
43) Import train labels to a pandas dataframe and create tain_Y.
44) Select best model from cross validation using train set among Random forest, Cat boost, XGBoost
45) Among above models random forest gives the highest accuracy.
46) Therefore random forrest model will be used for final prediction.
47) Select features using sequential feature selection.
48) Selected features used for final prediction.
