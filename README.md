**Python Script for Extracting and Processing Bank Data (ETL)**  
This Python script implements an Extract-Transform-Load (ETL) process to collect, transform, and store data from a website. The script focuses on extracting information about the largest banks and their market capitalization (MC) in USD billion.

**Key functionalities:**  
  
**Data Extraction:**  
Fetches data from a specified URL (currently a historical archive of Wikipedia's "List of largest banks").
Parses the HTML content using BeautifulSoup to identify relevant tables and rows.
Extracts the bank name and market cap (USD billion) and stores them in a Pandas DataFrame.  

**Data Transformation:**  
Reads exchange rate information from a CSV file.
Adds three new columns to the DataFrame containing the market cap converted to GBP, EUR, and INR (rounded to two decimals).  

**Data Loading:**  
Saves the final DataFrame to a CSV file.
Establishes a connection to a SQLite database (Banks.db).
Creates a table named Largest_banks and populates it with the DataFrame.
Executes sample queries on the database table to display data and perform basic analysis.

**Additional features:**  
Comprehensive logging using a dedicated function log_progress to track the script's execution stages.
Error handling can be further implemented for situations like failed data extraction or database connection issues.

**Code Overview**  
_log_progress_: Logs the progress of the ETL process.  
_extract:_ Extracts data from the specified URL and returns it as a DataFrame.  
_transform:_ Reads exchange rates from a CSV file and adds converted GDP columns to the DataFrame.  
_load_to_csv:_ Saves the DataFrame to a CSV file.  
_load_to_db:_ Loads the DataFrame into a SQLite database.  
_run_query:_ Executes SQL queries on the database and prints the results.  

