# Features and Definitions

amount_tsh - Total static head (amount water available to waterpoint)
date_recorded - The date the row was entered
funder - Who funded the well
gps_height - Altitude of the well
installer - Organization that installed the well
longitude - GPS coordinate
latitude - GPS coordinate
wpt_name - Name of the waterpoint if there is one
num_private - No definition
basin - Geographic water basin
subvillage - Geographic location
region - Geographic location
region_code - Geographic location (coded)
district_code - Geographic location (coded)
lga - Geographic location
ward - Geographic location
population - Population around the well
public_meeting - True/False
recorded_by - Group entering this row of data
scheme_management - Who operates the waterpoint
scheme_name - Who operates the waterpoint
permit - If the waterpoint is permitted
construction_year - Year the waterpoint was constructed
extraction_type - The kind of extraction the waterpoint uses
extraction_type_group - The kind of extraction the waterpoint uses
extraction_type_class - The kind of extraction the waterpoint uses
management - How the waterpoint is managed
management_group - How the waterpoint is managed
payment - What the water costs
payment_type - What the water costs
water_quality - The quality of the water
quality_group - The quality of the water
quantity - The quantity of water
quantity_group - The quantity of water
source - The source of the water
source_type - The source of the water
source_class - The source of the water
waterpoint_type - The kind of waterpoint
waterpoint_type_group - The kind of waterpoint

Total -- 39 features and 1 target


# Clean Up

### Target 
status_group             59072 non-null int64     *three categories (ternary classification) 

### To delete
id                       59072 non-null int64     *not relevant*
funder                   55439 non-null object    *not relevant*
wpt_name                 59072 non-null object    *not relevant*
date_recorded            59072 non-null object    *turn into a datetime number*
installer                55419 non-null object    *too many categories to simplify*
recorded_by              59072 non-null object    *only 1 unique value - not relevant*
lga                      59072 non-null object    *repetative info*
ward                     59072 non-null object    *repetative info*
scheme_name              30932 non-null object    *too many missing features*
subvillage               58701 non-null object    *too many categories - repetative info*
region                   59072 non-null object    *21 categories - repetative info*
management               59072 non-null object    *12 categories - repetative info*
extraction_type          59072 non-null object    *too many categories - repetative info*
extraction_type_group    59072 non-null object    *too many categories - repetative info*
scheme_management        55197 non-null object    *repetative info*
payment_type             59072 non-null object    *repetative info*
quality_group            59072 non-null object    *repetative info*
quantity_group           59072 non-null object    *repetative info*
source                   59072 non-null object    *repetative info*
source_type              59072 non-null object    *repetative info*
waterpoint_type_group    59072 non-null object    *repetative info*


### Continuous
amount_tsh               59072 non-null float64    *70% are zero, no outliers, going to bin*
longitude                59072 non-null float64    *Some zeros, no outliers*
latitude                 59072 non-null float64    *Mostly negative numbers - which seems correct*
gps_height               59072 non-null int64      *Some zeros and negatives (not sure why) and a few outliers*
region_code              59072 non-null int64      *Lots of zeros, no outliers*
district_code            59072 non-null int64      *Lots of zeros, no outliers*
population               59072 non-null int64      *30% are zero, a few outliers - going to bin*
construction_year        59072 non-null int64      *30% are zero - going to bin*
num_private              59072 non-null int64      *98% are zeros, no outliers, going to bin*

       
### Categorical
public_meeting           55743 non-null object     *replaced null values with median (2 categories, True/False)*
permit                   56017 non-null object     *replaced null values with median (2 categories, True/False)*
basin                    59072 non-null object     *(9 categories) - one hot encoding*
extraction_type_class    59072 non-null object     *(7 categories) - one hot encoding down to 5 *
management_group         59072 non-null object     *(5 categories) - one hot encoding down to 2 *
payment                  59072 non-null object     *(6 categories) - one hot encoding down to 5 *
water_quality            59072 non-null object     *(8 categories) - one hot encoding down to 2 *
quantity                 59072 non-null object     *(5 categories) - one hot encoding down to 2 *
source_class             59072 non-null object     *(3 categories) - one hot encoding down to 2 *
waterpoint_type          59072 non-null object     *(6 categories) - one hot encoding down to 3 *





