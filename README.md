# Hotel-Data-Analysis
The "Hotel Data Analysis" project aims to uncover insights into user preferences, revenue streams, and engagement patterns in the hotel sector, specifically focusing on our establishment. Through rigorous analysis, we seek to inform strategic decisions and enhance operational efficiency.

Technologies Used:
•	 MySQL Workbench:  MySQL was used to store and manage the structured data, making it accessible for analysis and reporting.  
•	 Power BI: Power BI was used to generate interactive reports and dashboards, enabling stakeholders to explore the project’s findings.

Project Highlights: 

•	Data Preparation: Describe any significant data preprocessing steps, such as data cleaning, transformation, or feature engineering.

•	SQL Queries: Highlight key SQL queries or operations performed on the database.

•	Visualization: Mention the main visualizations created using Power BI, and how they contribute to the project’s objectives.

•	Insights: Summarize the key insights or findings derived from the analysis.



Folder Structure:

•	DataBase : This folder contains the data of different years and Tables.

•	Power Bi Dashboard: This folder contains the ‘POWER BI Dashboard’ for visualizations.

•	SQL Work : This folder contains the ‘SQL WORK’ .


SQL WORKS (Some of SQL Queries) –

•	TO JOIN ALL THE TABLES
create table hotels as (
(select * from eighteen)
union
(select * from ninteen)
union
(select * from twenty));

Note: Here I assigned the name of all tables as their number of the year. Like 2018 as ‘eighteen’ and 2019 as ‘ninteen’.


•	TO GET REVENUE(TOTAL NIGHT STAYS*ADR) AS PER YEARS AND HOTELS.
select 
arrival_date_year, hotel,
round(sum((stays_in_week_nights+stays_in_weekend_nights)*adr),2) as revenue
from hotels
group by arrival_date_year,hotel;

•	TO JOIN LEFTOUT TABLES ON THE BASIS OF SIMILAR COLUMN
select * from hotels
left join project.market_segment
on hotels.market_segment=market_segment.market_segment
left join project.meal_cost
on meal_cost.meal=hotels.meal;
