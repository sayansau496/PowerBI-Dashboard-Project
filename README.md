


















 

































SAYAN SAU
 
CONTENT




1.	PROJECT DESCRIPTION
2.	REQUIREMENT GATHERING

3.	VISUALS AND GRAPHS

4.	CHARTS AND GRAPHS

5.	KEY TAKEAWAYS

6.	CONCLUSION
7.	SOURCE FILES
 
PROJECT DESCRIPTION

Power BI has become an essential tool for transforming raw data into meaningful stories, and this project is a prime example of that power in action. By analyzing road accident data, we’ve moved beyond simple spreadsheets to create a dynamic, visual narrative that highlights critical safety trends and patterns.

This dashboard was designed to take a complex dataset and make it immediately understandable for anyone looking to improve road safety. Using Power BI’s interactive features, we can see exactly how different variables—like road types, light conditions, and locations —contribute to the overall picture of traffic incidents. By visualizing casualties based on Light Conditions (73.8% during the day) and Urban vs. Rural areas (61.9% in urban settings), we can pinpoint when and where risks are highest.

The heart of this project lies in tracking key performance indicators for 2022, such as the encouraging 11.9% decrease in total casualties compared to the previous year. Infrastructure also tells a significant story, with a staggering 145K casualties occurring on single carriageways, suggesting that road design is a massive factor in driver safety. Through the monthly trend analysis for 2021 and 2022, we can identify seasonal spikes, showing how accident rates fluctuate throughout the year. Ultimately, this Power BI project isn't just about displaying numbers; it's about providing a tool that helps stakeholders make data-driven decisions to save lives.









Requirement Gathering



	Primary KPI 1: Total Casualties and Total Accident values for 2022 and YoY growth.
	Primary KPI 2: Total Casualties by Accident Severity for 2022 and YoY growth.
	Secondary KPI: Total Casualties with respect to Vehicle Type for 2022.
	Monthly Trend showing comparison of casualties for 2021 & 2022.
	Casualties by Road Type for 2022.
	Casualties in 2022 by Area/Location & Day/Night.
	Total Casualties and Total Accidents by Location.
 
VISUALS AND FORMULAS

Visual Use Cases
In this dashboard, every chart serves a specific purpose, turning a massive dataset of road incidents into an intuitive story that even a non-technical viewer can follow. We chose these visuals based on their ability to highlight different layers of risk:

•	KPI Cards for Instant Impact: These are placed at the top to provide the "big picture" numbers, such as the 195.7K total casualties and the 2.9K fatal incidents recorded in 2022. They give the viewer an immediate benchmark before they dive into the details.
•	Donut Charts for Proportional Analysis: We used these to break down casualties by Urban vs. Rural areas and Light Conditions. Since these categories only have two or three variables, the donut chart makes it easy to see at a glance that Urban areas (61.95%) and Daylight (73.84%) are where the vast majority of incidents occur.
•	Bar Charts for Comparative Ranking: The bar chart for Road Type is essential for identifying infrastructure risks. It clearly ranks Single Carriageways at the top with 145K casualties, showing a significant safety gap compared to roundabouts or slip roads.
•	Area Charts for Trend Identification: By plotting the Monthly Trend, we can compare 2021 and 2022 side-by-side. This visual helps us see if certain months—like the year-end peak in November—are consistently more dangerous, which is vital for seasonal planning.



DAX Formulas and Logic
The "brain" of this Power BI project is the DAX (Data Analysis Expressions) used to calculate specific metrics. These formulas allow the dashboard to be dynamic, updating the totals and percentages automatically as filters are applied.

1.	Primary Casualty Counts
To get the foundation of the report, we sum up the casualty column. This is the base for almost every other calculation in the project.

Total Casualties = SUM(Data[Number_of_Casualties])

2.	Year-to-Date (YTD) Comparisons
 
To calculate the 195.7K for 2022 and compare it to the previous year's performance, we use time-intelligence functions.

CY Casualties = TOTALYTD([Total Casualties], 'Date'[Date])



3.	Year-over-Year (YoY) Growth
The dashboard highlights an 11.9% decrease in total casualties. This is calculated by comparing the current year to the previous year to measure the effectiveness of road safety measures.

YoY Change = DIVIDE([CY Casualties] - [PY Casualties], [PY Casualties])

4.	Severity Filtering
To break the data down into Fatal (2.9K), Serious (27.0K), and Slight (165.8K) casualties, we use the CALCULATE function to "slice" the total sum by the accident severity column.

Serious Casualties = CALCULATE([Total Casualties], Data[Severity] = "Serious")
 
Charts and Graphs


1.	Overall KPI Cards (Top Summary Tiles):


The KPI cards summarize overall road accident statistics for 2022, including total casualties, total accidents, and casualty severity. The year-on-year decline across most indicators reflects positive progress in road safety efforts. However, the magnitude of the numbers underscores the continuing need for sustained interventions and policy focus.


2.	Monthly Casualties Trend (2021 vs 2022 – Line Chart):

 
This line chart illustrates the month-wise trend of road accident casualties for the years 2021 and 2022. While both years follow a broadly similar pattern, casualties in 2022 remain consistently lower than in 2021, indicating an overall improvement. The mid-year rise suggests increased traffic activity, whereas the decline toward the end of the year may reflect reduced travel or effective safety interventions.


3.	Casualties by Road Type (Horizontal Bar Chart)

This chart highlights the distribution of casualties across different road types. Single carriageways account for the highest number of casualties by a significant margin, indicating higher risk on such roads. In contrast, dual carriageways and roundabouts show comparatively lower casualty figures, suggesting that better road infrastructure and controlled traffic flow contribute to improved safety.

4.	Casualties by Urban vs Rural Area (Donut Chart)


 
The donut chart presents the proportion of casualties occurring in urban versus rural areas. Urban areas contribute the majority of casualties, which can be attributed to higher traffic density and frequent interactions between vehicles and pedestrians.
However, the rural share remains substantial, emphasizing that road safety remains a concern beyond city limits.

5.	Casualties by Light Conditions (Donut Chart)


This visualization shows casualties segmented by light conditions. Most casualties occur during daylight hours, largely due to increased traffic volume during the day. Although fewer casualties occur in dark conditions, the risk remains significant, highlighting the importance of adequate lighting and visibility measures during night-time travel.

6.	Casualties by Location (Map Visualization)


 
The map provides a geographic representation of road accident casualties across different regions. Higher concentrations are visible in densely populated and high-traffic areas, indicating regional patterns in road safety risks. This visualization helps identify locations that may require targeted policy measures and infrastructure improvements.


Key Takeaways


•	Overall decline in accidents and casualties
The dashboard indicates a noticeable reduction in total accidents and overall casualties in 2022 compared to the previous year. Declines are observed across fatal, serious, and slight casualty categories, suggesting that road safety measures and enforcement may be having a positive impact.
•	Casualties remain concentrated in urban areas
Urban regions account for a significantly higher proportion of casualties than rural areas. This highlights the influence of traffic density, congestion, and frequent interactions between vehicles and pedestrians in urban environments.
•	Single carriageways pose the highest risk
Among all road types, single carriageways record the highest number of casualties by a wide margin. In contrast, dual carriageways and roundabouts show comparatively lower casualty figures, emphasizing the role of road design and infrastructure in improving safety.
•	Daylight conditions see more accidents due to higher exposure
Most casualties occur during daylight hours, primarily because traffic volumes are higher during the day. While fewer accidents occur in dark conditions, the associated risks remain substantial and should not be overlooked.
•	Private vehicles contribute the largest share of casualties
Cars account for the majority of casualties among vehicle types, reflecting their widespread usage. Two-wheelers also represent a notable share, indicating the need for focused safety awareness and protective measures for vulnerable road users.
•	Clear seasonal and monthly trends are visible
The monthly trend analysis shows consistent patterns across both years, with casualty numbers rising during certain months and declining toward the year-end. This suggests seasonal factors and travel behavior play a role in accident frequency.
•	Geographical clustering highlights high-risk regions
The map visualization reveals dense clusters of accidents in specific locations, particularly in populated and high-traffic areas. These hotspots can help authorities prioritize targeted interventions and infrastructure improvements.
 
CONCLUSION

This Road Accident Analysis dashboard provides a comprehensive overview of accident patterns and casualty trends using data-driven insights. The analysis indicates an overall reduction in accidents and casualties in 2022, reflecting progress in road safety initiatives and enforcement measures. However, the persistence of high casualty numbers highlights that road safety remains a critical concern.



The findings reveal that urban areas, single carriageways, and daylight conditions contribute disproportionately to accident occurrences, emphasizing the impact of traffic density, road design, and exposure levels. Additionally, private vehicles and two-wheelers emerge as key contributors to casualties, underscoring the need for targeted awareness campaigns and stricter compliance with safety regulations.



By combining trend analysis, categorical breakdowns, and geographic visualization, the dashboard enables stakeholders to identify high-risk areas and underlying factors influencing road accidents. These insights can support informed decision-making, targeted interventions, and long-term policy planning aimed at reducing accidents and improving overall road safety 

