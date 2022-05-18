# fuel-economy-data-analysis
This project is on analyzing fuel economy data provided by the Environmental Protection Agency.

For notebook 1 (`assessing.ipynb`),
I performed exploratory data analysis on the 2008 and 2018 datasets.


For notebook 2 (`cleaning.ipynb`),
I cleaned the dataset by removing some unnessary columns. I renamed all the column for consistency between the two datasets.
The output files are `data_08_v1.csv` and `data_18_v1.csv`


For notebook 3 (`filter_drop_dedupe.ipynb`), 
-Filter
For consistency, only compare cars certified by California standards. Filter both datasets using query to select only rows where cert_region is CA. Then, drop the cert_region columns, since it will no longer provide any useful information (we'll know every value is 'CA').
- Drop Nulls
Drop any rows in both datasets that contain missing values.
- Dedupe
Drop any duplicate rows in both datasets.

The output files are `data_08_v2.csv` and `data_18_v2.csv`


For notebook 4 (`fixing_datatype_cyl.ipynb`),
Extract the integer from the string in the `cyl` column of the 2008 dataset
Convert the datatype of the `cyl` column of the 2018 dataset from float to integer

The output files are `data_08_v3.csv` and `data_18_v3.csv`


For notebook 5 (`fix_datatypes_air_pollution.ipynb`),
I get an error when I try to convert the air_pollution_score from string to float. Some rows in the datasets have two values for fuel type. As a result, there are also two values for the following columns: 'air_pollution_score', 'city_mpg', 'hwy_mpg', 'cmb_mpg', 'greenhouse_gas_score'.
I created new records for these rows with multiple values, and then appended it to the original dataframe.
After this, I was able to convert the air_pollution_score column from string to float.

The output files are `data_08_v4.csv` and `data_18_v4.csv`

For notebook 6 (`fix_datatypes_mpg_greenhouse.ipynb`),
I fixed the datatypes in city_mpg, hwy_mpg, cmb_mpg and greenhouse_gas_score columns.
I confirmed that the two datasets had consistent formats and data types.

The output files are `clean_08.csv` and `clean_18.csv`

For notebook 7 (`exploring_visuals.ipynb`),
I checked the histogram distibution of some variables in the 2008 dataset and compared it to the 2018 histogram distribution to see if there are any difference.
I also checked the correlation between some variables using scatter plots.

For notebook 8 (`merging_data.ipynb`),
I merged the two datasets using Pandas inner merge.

The output file is `combined_dataset.csv'

For notebook 9 (`result_merged.ipynb`),
I answered the question "For all of the models that were produced in 2008 that are still being produced now, how much has the mpg improved and which vehicle improved the most?"
