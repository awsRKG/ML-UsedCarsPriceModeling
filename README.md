# ML-UsedCarsPriceModeling
Modeling various features of used card to determine the key drivers of price.

Business Understanding : Use the dataset to unterstand the correlation between various features/attributes of used car and the price and identify the key drivers. This helps the business to predict the price of a car based on its features so that they can make informed decisions in setting the sale price of used cars and in procuring more cars for resale.

Data Understanding :
The data in this dataset is tabular, with rows and columns, where each row represents a specific used car listing, and each column represents a particular attribute or feature of these cars.

Features - 
Region,
Price, 
Year, 
Manufacturer, 
Model, 
Condition, 
Cylinders, 
Fuel, 
Odometer, 
Title_status, 
Transmission, 
VIN, 
Drive, 
Size, 
Type, 
Paint_color, 
State

Some features are catergorical values (eg: title_status) and some are continuous values (eg: odometer). There are a total of 426879 entries in the dataset but several of them has null/nan values for at-least one column

Data Preparation :
Cleaned the dataset by removing the columns that have missing/nan values in more than 30%
Deleted the model column as it contains open ended text and has too many possible values, likely uninformative
Checked and removed the outliers for Price and Odometer columns (>1000000)
Deleted the "Region" and "State" columns as they seem to have too many possible values and less correlation to the price
Converted categorical variables into dummy/indicator variables using pandas.get_dummies
Split the dataset into Train and Test datasets

Evaluation: 
For each of the regression models, Mean Squared error has bee computed for the Training and Test datasets.

The MSE values for all these models came out to be similar. The Lasso regression did not fully converge. Ridge regression using GridSearch took long time given the size of the data. Difference between test and training MSEs are not that high.

Best model and other models detected these features as the most influencing features in determining the price of an used car Year (Newer the car, higher the price) Odometer (lower the odometer, higher the price) fuel type (diesel vs gas vs electric seems to have impact on the price).

Deployment:
Deploy the best model from GridSearch. Upload Readme and jupyter notebook to GIT Hub.¶
