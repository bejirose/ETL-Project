# etl-project-Team3

PURPOSE

To use multiple data sources to find data job titles, average salaries and salaries by region.

1. Source 1: http://indeed.com/salaries
2. Source 2: Kaggle CSV files (file for each job title category)
3. Source 3: https://www.calu.edu/academics/undergraduate/bachelors/data-science/what-can-you-do-with-a-statistics-and-data-science-degree.asp

PROCESS

1. Scrape source # 1 - Start with a list of job titles. Fill Indeed search field for each title and click "Search". This shows results page with 
average salary and other details. The key challenge was that indeed search field pops a drop-down mouse_over list and by deafult only searches 
for first option. Splinter was used to mouse_over last option that allows "popular search for the specific title desired". Second challenge was 
the classes would change based on indeed loading two different type of search pages on same URL. The scraped data is stored in a pandas dataframe.

2.

3.

4. MERGE
