# pump_it_up_competition

Repo link: https://github.com/DARathnasiri/pump_it_up_competition

##
1) Required packages are imported.<br/>
2) Train values and test values are imported to pandas dataframes.<br/>
3) Create a combined pandas dataframe of train values and test values.<br/>

## Explotary data analysis
4) Plot graphs for each feature for explotary data analysis using seaborn and see overview of the data.<br/>

## Handling Outliers
5) amount_tsh, construction_year, longitude features has outliers.<br/>
6) 0 outlier values in construction_year features replace with mean of the non zero values of construction_year.<br/>
7) 0 outlier values in longitude features replace with mean of the non zero values of longitude.<br/>

## Modify features
8) id feature is a unique value to each row.<br/>
9) Therefore id is not useful for predictions.<br/>
10) Therefore id feature is dropped.<br/>
11) num_private feature is not a useful value for predictions.<br/>
12) Therefore num_private feature is dropped.<br/>
13) The recorded_by column has only one value.<br/>
14) Therefore it is not useful for predictions.<br/>
15) Therefore recorded_by feature is dropped.<br/>
16) Installer feature has 0 values. They are unknown values.<br/>
17) Therefore 0 values replaced with 'missing' value in installer.<br/>
18) Installer feature has missing values.<br/>
19) Missing values in installer feature are filled with 'missing' value.<br/>
21) Replace the spelling mistakes and collect same categories in same name in installer feature.<br/>
22) Installer values which has less than 400 value counts collect together and named them 'others'.<br/>
23) Funder feature has 0 values. They are unknown values.<br/>
24) Therefore 0 values replaced with 'missing' value in funder.<br/>
25) Funder feature has missing values.<br/>
26) Missing values in funder feature are filled with 'missing' value.<br/>
27) Funder values which has less value counts collect together and named them 'others'.<br/>

## Feature scaling
28) Float and integer features are scaled using standard scaler.<br/>
29) Standard scaler produce more accuracy in prediction than the min max scaler.<br/>
30) scale amount_tsh, latitude, longitude, gps_height, population features are scaled using standard scaler.<br/>

## Encode features
31) All object features (not ineger and float) are label encoded.<br/>

## Filling missing values
32) scheme_name, scheme_management, public_meeting, permit, subvillage features still have missing values.<br/>
33) Since 0.4749 of scheme_name values are missing, scheme_name column is dropped.<br/>
34) Analyse correlation of the scheme_management column with other columns.<br/>
35) scheme_management has high correlation with management_group.<br/>

management_group -----> highest frequncy scheme_management value<br/>
0  --------------------------------------> 6<br/>
1  --------------------------------------> 1<br/>
2  --------------------------------------> 8<br/>
3  --------------------------------------> 0<br/>
4  --------------------------------------> 0<br/>

36) Missing vales of scheme_management are filled with values that has highest frequency in each management_group shown in the above table.<br/>
37) Analyse correlation of the public_meeting column with other features.<br/>
38) public_meeting has high correlation with management_group.<br/>

management_group  ---->   highest frequncy public_meeting value<br/>
0 ----------------------------------------> 0<br/>
1 ----------------------------------------> 0<br/>
2 ----------------------------------------> 0<br/>
3 ----------------------------------------> 0<br/>
4 ----------------------------------------> 0<br/>

39) Missing values of public_meeting are filled with values that has highest frequency in each management_group shown in the above table.<br/>
40) Consider missing values in permit as a seperate class and do the label encoding.<br/>
41) Consider missing values in subvillage as a seperate class and do the label encoding.<br/>

##

42) Divide combined pandas dataframe to train pandas dataframe and test pandas dataframe.<br/>
43) Import train labels to a pandas dataframe and create tain_Y.<br/>
44) Select best model from cross validation using train set among Random forest, Cat boost, XGBoost<br/>
45) Among above models random forest gives the highest accuracy.<br/>
46) Therefore random forrest model will be used for final prediction.<br/>
47) Select features using sequential feature selection.<br/>
48) Selected features used for final prediction.<br/>
