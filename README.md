# Project Name: ETL Project
## Team3: Ashish Desai, Bejirose K. Stanly, Poonam Kushwaha

**PURPOSE**

To use multiple data sources to find data job titles, average salaries and salaries by region.

**SOURCES**

1. Source 1: http://indeed.com/salaries
2. Source 2: https://kaggle.com: Kaggle CSV files (file for each job title category)
3. Source 3: https://www.calu.edu/academics/undergraduate/bachelors/data-science/what-can-you-do-with-a-statistics-and-data-science-degree.asp

**ETL PROCESS**

1. EXTRACT & TRANSFORM STEPS

    1.1 Scrape source # 1 - Start with a list of job titles. Fill Indeed search field for each title and click "Search". This shows results page with average salary and other details. The key challenge was that indeed search field pops a drop-down mouse_over list and by deafult only searches for first option. Splinter was used to mouse_over last option that allows "popular search for the specific title desired". Second challenge was the classes would change based on indeed loading two different type of search pages on same URL. The scraped data is stored in a pandas dataframe.

    1.2. Kaggle Source # 2 - Downloaded three csv (DataAnalyst,DataEngineer,DataScientist) file from Kaggle in which we can see Job title, Salary estimate and location. Reading    data from CSV file and did transformation on juper notebook. The challenging part was salary estimate column, need to first split the column to lower & upper salary then repplace K,$ or any special character with zero's, cleaning the data. To get average salary did typecast on lower & Upper column. After Transfformation moved/insert the data in stage and then did cleaning/calculation/transformation at database level and moved/insert in new final/reporting table.

    1.3. Scrape Source # 3 - Scraped job titles and Salary info from www.calu.edu using BeautifulSoup and loaded these 16 lists of job title dictionaries along with salary to Postgres SQL. These job titles are in turn used to extract more detailed information from indeed.com. There was a challenge in extracting job title information as the job title, a brief description about the job, and salary were all listed as one paragraph without having separate headings for this info. So had to take each list and search through the text to find out the job title and the salary list.

2. MERGE & LOAD STEP

    Merged the data from all three sources to one Jupyter notebook called salary.ipynb. For this project, all the data extraction, transformation, and loading processes are combined in salary.ipynb. All CSV files and Postgres schema files are in the "Resources" folder. Output files in csv format are in the "output" folder. We used the relational database, PostgreSQL to store the data. Tables are in the DB called, etl_db. Final source and output files are in the "Team3-etl-Final" folder.
