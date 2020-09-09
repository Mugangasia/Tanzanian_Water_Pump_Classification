# Pump-It-Up Competition Model

![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/water-1227680_1280.jpg)
 *A old waterpump has found a new flow in data science, Source: MoreLight, Pixbay.com*

## Flatiron Mod 3 V2.1 Final Project


## README Outline
* Introduction 
* Project Summary
* Repo Contents
* Prerequisites
* Feature and Definitions
* Results
* Future Work
* Built With, Contributors, Authors, Acknowledgments


## Introduction - A Classification Model
The main goal of this project is to demonstrate the skills we have learned in Module 3 that revolve around machine learning and the building of a classification model. I chose a dataset that would allow me to preprocess, explore it, and then build a classification model that allows me to interpret the original question. 

![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/tanzania-flag-small.png)
 *Tanzanian Flag - I had to do some research on the country in order to help make my plan.*


## Project Summary
The best overall model was the simple Random Forest with criterion='entropy' and all rows with missing values deleted. This model was able to predict water-points with 0.8144 accuracy and had similar values for precision and recall.

![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/Waterpoint_Status.png)
 *A brief look at all the Training Data waterpoints*

GridSearch was able to improve my basic XGBBoost model to 0.8103 along with extensive cleaning of the data. The large percentage of categorical data columns, at least a third of which were repetitive or overlapping, made it difficult to sort through and decide on features that were most relevant. As well, the multiple continuous features that contained either a high percentage of zeros or more missing data made many of these features also unusable or irrelevant.

While it might be a waste of time and resources to visit a possibly non-functioning water-point only to find that it was in fact still working - I believe it is better to error on the side of having too many false positives as opposed to letting people go without a safe drinking water source.


## Libraries & Prerequisites
These are the libraries that I used in this project.
* numpy as np
* pandas as pd
* matplotlib.pyplot as plt
* %matplotlib inline
* seaborn as sns
* folium
* datetime as dt
* from sklearn.model_selection import train_test_split 
* from sklearn.model_selection import cross_val_score
* from sklearn.model_selection import GridSearchCV
* from sklearn.metrics import accuracy_score 
* from sklearn.metrics import f1_score 
* from sklearn.metrics import confusion_matrix 
* from sklearn.metrics import classification_report
* from sklearn.metrics import confusion_matrix
* from sklearn.linear_model import LogisticRegression
* from sklearn.ensemble import RandomForestClassifier
* import xgboost as xgb


## Repo Contents
This repo contains the following:
* README.md - this is where you are now!
* Final_Notebook.ipynb - the Jupyter Notebook containing the finalized code for this project.
* LICENSE.md - the required license information.
* Blog Post - the link to my Medium blog post pertaining to this project.
* training_set_values.csv - the file containing the dataset values.
* training_set_target.csv - the file containing the dataset target.
* test_set_values.csv - the file containing the dataset test values (which I didn't use for this project).
* CONTRIBUTING.md 
* module_3_project_features_and_definitions.md
* mod_3_project_guidelines - an explanation of the project from Flatiron.
* mod_3_project_video_link - https://drive.google.com/file/d/1krMLpPaSvyQC-B7Vq6T62WuytGTXf_k8/view?usp=sharing
* mod_3_project_rubric - a review of the highlighted features for this Flatiron project
* mod_3_project_slideshow pdf 
 (slideshow link https://docs.google.com/presentation/d/1hGLtq9iZbrOJ6ii0f5pA6VmMGeQmwfmN5voG5W2CLqU/edit?usp=sharing)
* Images - all images.


## Feature and Definitions
- amount_tsh - Total static head (amount water available to waterpoint)
- date_recorded - The date the row was entered
- funder - Who funded the well
- gps_height - Altitude of the well
- installer - Organization that installed the well
- longitude - GPS coordinate
- latitude - GPS coordinate
- wpt_name - Name of the waterpoint if there is one
- num_private - No information
- basin - Geographic water basin
- subvillage - Geographic location
- region - Geographic location
- region_code - Geographic location (coded)
- district_code - Geographic location (coded)
- lga - Geographic location
- ward - Geographic location
- population - Population around the well
- public_meeting - True/False
- recorded_by - Group entering this row of data
- scheme_management - Who operates the waterpoint
- scheme_name - Who operates the waterpoint
- permit - If the waterpoint is permitted
- construction_year - Year the waterpoint was constructed
- extraction_type - The kind of extraction the waterpoint uses
- extraction_type_group - The kind of extraction the waterpoint uses
- extraction_type_class - The kind of extraction the waterpoint uses
- management - How the waterpoint is managed
- management_group - How the waterpoint is managed
- payment - What the water costs
- payment_type - What the water costs
- water_quality - The quality of the water
- quality_group - The quality of the water
- quantity - The quantity of water
- quantity_group - The quantity of water
- source - The source of the water
- source_type - The source of the water
- source_class - The source of the water
- waterpoint_type - The kind of waterpoint
- waterpoint_type_group - The kind of waterpoint


## Models
These are the models that I used in this project.
#### Logarithmic
#### Random Forest
#### Random Forest with Grid Search
#### XGBoost

![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/Feature_Importance.png)
 *I used feature importance to help me guide my research and model building*


## Conclusion
My research found that payment types of 'monthly', 'annually', and 'per bucket' were the most efficient - which makes sense compared to 'free' or 'unknown' potable water! Obviously, waterpoints with a payment system were less likely to need repair.

![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/Basin_Status.png)
 *Bar graph of Waterpoint Status by Basin*

'Hand-pumps' and 'standpipes' were the most likely extraction types to remain functional. Therefore, the replacement of any of the broken or non-functioning wells should be converted to a more durable and dependable source if possible.

![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/Waterpoint_Basin.png)
 *Horizontal bar graph of all the different basins*

All models seem to point toward location as a highly valuable aspect of determining water-point status. While certain 'Water Basins' were more likely to have a higher percentage of either non-functioning water sources or water-points in need of repair, there is evidence that this could also be based on the regions' climate, amount of rainfall, population, and economic development.


## Future Work
As a way to increase the accuracy of supervised learning models, I would like to see better information on number of people who are using pumps on a daily or weekly basis and number of visits per given period.

Though my highest recommendation for future work would be to focus on the quality and cleanliness of water - as this is certainly one of the most important functions to a healthy community.

Any data that points to when a water-point was last serviced or replaced as well as a list of issues (i.e. broken handle, no water, power outages) would be beneficial to future models.

A more regulated collection of information and more precise entry of specific data is needed (water-point age, certain types, number of people using, etc.) in addition to a more standard set of options - such that location, payment, and source could be standardized, thus eliminating much of the missing data.

It might also be helpful to know how to measure the amount of water that is available - the 'amount_tsh' feature seems like it could be very useful but this information would need to be clearly measured as well as the method specifically described in detail.


## Competition
While I had hoped for a slightly higher score, it is important to keep in mind that the **BEST** score was only aroun 0.80 - and this competition included data scientists from around the world, both amature and experienced coders alike!
![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/Submission_score.png)
 *My score from the DataDriven Competition*


![](https://raw.githubusercontent.com/twhipple/dsc-mod-3-project-v2-1/master/Images/kenya-africa-1-1365025-1279x874.jpg)
 *The Serengeti - a dry place without much water! Source: Dave Dyet, FreeImages.com*


## Built With:
Jupyter Notebook
Python 3.0
scikit.learn

## Contributing
Please read CONTRIBUTING.md for details

## Authors
Thomas Whipple
Flatiron Academy

## License
Flatiron Academy - see the LICENSE.md file for details

## Acknowledgments
Thank you to my cohort team for all of their suggestions and to our instructor Abhineet Kulkarni.

