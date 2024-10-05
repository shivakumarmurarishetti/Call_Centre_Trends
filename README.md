# PwC Power BI Virtual Case Experience – Call Centre Trends

## Overview
This project involves building a Power BI dashboard for the Call Center Manager to monitor key performance indicators (KPIs), including customer satisfaction, call handling metrics, and agent performance.

## Key KPIs
- Customer Satisfaction
- Calls Answered vs. Abandoned
- Call Volume by Time of Day
- Average Speed of Answer
- Agent Performance (Average Handle Time vs. Calls Answered)

## Data Source
- **Dataset:** PwC Call Centre Trends (10 columns, 5000 rows)
- **Preparation:** Data cleaned and transformed using Power Query in Power BI Desktop.

## Data Preparation
- Removed unnecessary columns and rows.
- Validated data types for all fields.

## Data Modeling
- Created a data model with relevant measures for KPIs, such as average speed of answer, customer satisfaction, and call resolutions.

## Key DAX Measures
- `Average Speed of Answer` = `AVERAGE('call centre trends'[Speed of answer in seconds])`
- `Positive Satisfaction Rating` = `CALCULATE(COUNT('call centre trends'[Satisfaction rating]), FILTER('call centre trends', 'call centre trends'[Satisfaction rating] IN {4,5}))`
- `Resolved Calls` = `COUNTX(FILTER('call centre trends', 'call centre trends'[Resolved] = "Yes"), 'call centre trends'[Resolved])`
- `Total Calls Answered` = `COUNTX(FILTER('call centre trends', 'call centre trends'[Answered (Y/N)] = "Yes"), 'call centre trends'[Answered (Y/N)])`

## Dashboard
- Created visualizations in Power BI covering overall trends, agent performance, and call resolutions.
- **Visuals include:**
  - Call Center Overview
  - Agent Performance Quadrant (Average Handle Time vs. Calls Answered)

## Insights
- Most satisfaction ratings are between 3 and 4.
- Customer satisfaction peaked in January, dropping by March.
- Most calls are received in the morning.
- Joe has the fastest response time, while Jim resolves the most calls despite a slower response rate.
- Becky has the lowest speed of answer but performs well in call resolution.
