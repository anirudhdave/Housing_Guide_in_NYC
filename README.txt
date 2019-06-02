1. Raw files and source mapping:

Sources for each raw file:
FIRST DATASET:   NYC Annual Housing Data
	'year_borough.xls' ==> https://www1.nyc.gov/site/finance/taxes/property-annualized-sales-update.page

(Note: Downloaded the “MS Excel” file for each borough for every year from 2010 - 2017 under Detailed Annual Sales Reports by Borough. 
So in total 40 files named by year, an underscore and borough, all lowercase and no spaces. 
2018 was not originally available when we first started this project)

SECOND DATASET: NYPD Complaint Data 
	'NYPD_Complaint_Data_Historic.csv' ==> https://data.cityofnewyork.us/Public-Safety/NYPD-Complaint-Data-Historic/qgea-i56i

(Note: Export the “csv” file from this link. This dataset includes all valid crimes reported to the New York City Police Department (NYPD) from 2006 to the end of last year (2017).

2A. Run the NYC_Housing_Data_file_1.ipynb file to clean the raw NYC housing data files and create the "clean" summary file. 
    -Before running this, you need to make sure you are running the most up to date version of pandas. 
    -The program will automatically pull in the raw files as long as they are in the same directory as the notebook, no need to change the directory name. 
    -The program will generate an output file named “Final_Median_Housing_Data.csv”. 
    -The output folder will need to be changed to the location you would like the file to be written to. 
    -The file created will have the median housing price for every zip code for every year along with the number of sales from 2010 to 2017. 

2B. Run the “crime_data_Data_file_2.ipynb” file to clean the raw NYPD complaint data. 
    -The current data source is hosted at local machine so if anyone wants to run this python program than he/she needs to first download the dataset from above 
		mentioned external link and then import it with Python. 
    -The program will generate an output file named “final_crime_file.csv”. 


3. Run the “sql_join_file_3.ipynb” file to join both “Final_Median_Housing_Data.csv” and “final_crime_file.csv”. 
    -First of all, a database named as "Final_Database.db" is created and placed it in the project folder. 
    -Input files (basically both CSVs) are hosted at local machine so if anyone wants to run this python program than he/she needs to
               first download the cleaned dataset from our project submission folder - you can get the “Final_Median_Housing_Data.csv” from “NYC Housing Data + Notebook” folder
               and “final_crime_file.csv” from “NYPD crime data + notebook” folder. 
    -Before joining, the number of rows in the “final_crime_file.csv” were around 3.9M and after doing the inner join with housing dataset, it fell down to 3.76M.
    -The program will generate an output file named “final_joined_file.csv”. 
	
4. For data visualization purpose we created the POC using Power BI and replicated most of the similar charts using Python - Matplotlib function.
  -You can find the Power BI file (“NYU DWD Project.pbix”) and Python script (DWD_project_plotting_file_4) in the “Data Visualization” folder.
  -The input file is hosted at local machine.
  -If anyone wants to run this python program than he/she needs to first download the dataset from “Joining” folder ? “final_joined_file.csv”.
  -The charts generated within this ipynb file are the final output of this program. 
  -These charts are written to the system every time the are plotted using the UDF defined in the DWD_project_plotting_file_4. 
  -The outputs are stored in the “Data Visualization” folder. 
  -If you wish to re-generate them using the notebook, change the directory that is set in the UDF code for a directory on your local system.
