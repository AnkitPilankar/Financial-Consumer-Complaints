Maven Financial Consumer Complaints challenge

![Capture](https://github.com/user-attachments/assets/318b4af8-2af6-4eb7-ae04-11486b618332)



OverView:

This project involves analyzing over 63,000 records of consumer complaints in the financial sector. The dataset includes details about various financial products and services, such as mortgages, credit cards, and bank accounts, as well as issues consumers faced and how companies responded to their complaints.


For this project, I worked with a dataset of consumer complaints sourced from the Consumer Financial Protection Bureau (CFPB), covering a variety of financial products and services. The data included information on complaint submissions, company responses, and resolution statuses such as "closed," "in progress," and "closed with monetary relief." The goal was to analyze trends and performance metrics related to how companies address consumer issues, including response timeliness and resolution effectiveness, while visualizing these insights in an interactive dashboard.

Key tasks included:

Developing a Year-over-Year (YoY) comparison to analyze complaint trends and seasonal patterns.

Creating detailed metrics for timely responses, types of company resolutions (e.g., monetary relief, explanation), and ongoing complaint statuses.

Implementing Field Parameters for financial products and sub-products, allowing interactive filtering for deeper data insights.

Using conditional formatting to visualize monthly and daily complaints distribution and highlight key trends.

Employing tooltips for enhanced data exploration, providing additional context on products and issues when hovering over visuals.


Key Metrics/KPIs Used:

Total Complaints: Total number of complaints received.

Average Days to Resolution: Average time taken to resolve complaints.

Timely Response Rate: Percentage of complaints responded to in a timely manner (Yes/No/Still Pending).

Complaint Resolution Status: 
Percentage of complaints closed, including:

Closed with Monetary/Non-Monetary Relief

Ongoing Complaints: Percentage of complaints still in progress.

Closed with Explanation

Closed with No Explanation

These KPIs provide insights into complaint handling efficiency, response timeliness, and the resolution quality.

Key Visualizations Created:

YoY Line Graph: Highlighting year-over-year trends in complaints.

Matrix of Complaints by Month and Day: Showing complaint distribution patterns across time.

Complaints by State: Visualizing geographic distribution of complaints.

Complaints Submission Method: Breakdown of how complaints were submitted (e.g., online, phone).

Total Complaints by Products: Insights into the most complained-about financial products.

Company Response to Public: Displaying how companies respond to complaints publicly, including transparency rates.

These visualizations provide a comprehensive view of complaint patterns, resolution times, and company transparency.

Dax used :
1) AVG days for resolution = avg(submitted date - receive date)
