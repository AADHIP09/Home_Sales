# Home_Sales

In this activity, I have used my knowledge of `SparkSQL` to determine key metrics about home sales data. Then, I used Spark to create temporary views, partition the data, cache and uncache a temporary table, and verify that the table has been uncached.

The below tasks were completed: 

Instructions

* Renamed the `Home_Sales_starter_code.ipynb` file as `Home_Sales.ipynb`.

* Imported the necessary PySpark SQL functions for this assignment.

* Read the *home_sales_revised.csv* data in the starter code into a Spark DataFrame.

* Create a temporary table called `home_sales`.

* Answer the following questions using `SparkSQL`:


1) What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.

    ![image](https://github.com/AADHIP09/Home_Sales/assets/135389893/2613a9f4-d330-4bfc-b184-21d406f066cc)

3) What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? Round off your answer to two decimal places.

    ![image](https://github.com/AADHIP09/Home_Sales/assets/135389893/ff3e49c8-34cf-45cf-835a-bdeeaf56de1b)

5) What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.

    ![image](https://github.com/AADHIP09/Home_Sales/assets/135389893/740ad560-51d8-4c42-82e9-c7a0dbfbac14)

4) What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.

   ![image](https://github.com/AADHIP09/Home_Sales/assets/135389893/e9b78846-ef8f-49c0-a392-2f1fb3714933)

* Cache the temporary table home_sales, and check if the table is cached

```
spark.sql("cache table home_sales")
``` 
* Check if your temporary table is cached.

```
spark.catalog.isCached('home_sales')
``` 

* Using the cached data, run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

   **Uncached runtime:** `1.199` seconds
  
    **Cached runtime:** `0.779` seconds 

* Partition by the `date_built` field on the formatted parquet home sales data.

* Create a temporary table for the parquet data.

* Run the query that filters out the view ratings with an average price of greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

  **Parquet runtime:** `0.543` seconds

  **Uncached runtime:** `1.199` seconds

* Uncache the home_sales temporary table.

```
spark.sql("uncache table home_sales")
``` 

* Verify that the home_sales temporary table is uncached using PySpark.
```
spark.catalog.isCached('home_sales')
```

* Download the `Home_Sales.ipynb` file and upload it into your `Home_Sales` GitHub repository.
