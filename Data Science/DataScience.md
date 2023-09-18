# **Many Models** Forecasting Solution using the **Prophet** package and **Microsoft Fabric**

### Convert the csv files to tables
1. Load ***dates.csv*** file to a table
1. Load ***forecast_data.csv*** file to a table
1. Load ***products.csv*** file to a table
1. Load ***stores.csv*** file to a table

### Run the forecast
1.	Import the required package and functions
1.	Retrieve the required data from the ***forecast_data*** data set that is needed to perform the forecast and stores the results in the ***store_item_history*** spark data frame.
1.	Define the data structure for the forecast.
1.	Define the function that will be used to perform the forecast on each store and item combination.
1.	Apply the forecast to the each partition defined in ***Step 4*** and save the results in a spark data frame named ***results*** and also in a temporary view named ***new_forecasts***.
1.	Create the table structure for the ***sales*** table which will hold the results of the forecast.
1.	Insert the forecast data into the ***sales*** table.

