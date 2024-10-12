Maven Financial Consumer Complaints challenge

Dataset : https://mavenanalytics.io/data-playground?order=date_added%2Cdesc&tags=Finance

Play WIth Dashboard : https://app.powerbi.com/groups/me/reports/f99f08ba-0bf5-4aa2-b400-174d1be2e3ff/ReportSection?experience=power-bi

![Capture](https://github.com/user-attachments/assets/318b4af8-2af6-4eb7-ae04-11486b618332)

![Capture 1](https://github.com/user-attachments/assets/69e1c8b2-46b5-456d-9ee4-d2b682909a3c)

![Capture10](https://github.com/user-attachments/assets/a7401f9d-a7ac-4b81-b622-96997012cadc)



OverView:

This project involves analyzing over 63,000 records of consumer complaints in the financial sector. The dataset includes details about various financial products and services, such as mortgages, credit cards, and bank accounts, as well as issues consumers faced and how companies responded to their complaints.


For this project, I worked with a dataset of consumer complaints sourced from the Maven Analytics Website, covering a variety of financial products and services. The data included information on complaint submissions, company responses, and resolution statuses such as "closed," "in progress," and "closed with monetary relief." The goal was to analyze trends and performance metrics related to how companies address consumer issues, including response timeliness and resolution effectiveness, while visualizing these insights in an interactive dashboard.

Key tasks included:

1)Developing a Year-over-Year (YoY) comparison to analyze complaint trends and seasonal patterns.

2)Creating detailed metrics for timely responses, types of company resolutions (e.g., monetary relief, explanation), and ongoing complaint statuses.

3)Implementing Field Parameters for financial products and sub-products, allowing interactive filtering for deeper data insights.

4)Using conditional formatting to visualize monthly and daily complaints distribution and highlight key trends.

5)Employing tooltips for enhanced data exploration, providing additional context on products and issues when hovering over visuals.


Key Metrics/KPIs Used:

1)Total Complaints: Total number of complaints received.

2)Average Days to Resolution: Average time taken to resolve complaints.

3)Timely Response Rate: Percentage of complaints responded to in a timely manner (Yes/No/Still Pending).

4)Complaint Resolution Status: 
Percentage of complaints closed, including:

Closed with Monetary/Non-Monetary Relief %

Ongoing Complaints: Percentage of complaints still in progress %

Closed with Explanation %

Closed with No Explanation %

These KPIs provide insights into complaint handling efficiency, response timeliness, and the resolution quality.

Key Visualizations Created:

1)YoY Line Graph: Highlighting year-over-year trends in complaints.

2)Matrix of Complaints by Month and Day: Showing complaint distribution patterns across time.

3)Complaints by State: Visualizing geographic distribution of complaints.

4)Complaints Submission Method: Breakdown of how complaints were submitted (e.g., online, phone).

5)Total Complaints by Products: Insights into the most complained-about financial products.

6)Company Response to Public: Displaying how companies respond to complaints publicly, including transparency rates.

These visualizations provide a comprehensive view of complaint patterns, resolution times, and company transparency.

Dax used :
1) AVG days for resolution = avg(submitted date - receive date)

2) Closed with explanation % = 
VAR ClosedExplanationCount = 
    CALCULATE(
        COUNT(Data[Complaint ID]), 
        Data[Company response to consumer] = "Closed with explanation"
    )
VAR TotalComplaints = COUNT(Data[Complaint ID])
RETURN 
IF(
    TotalComplaints = 0, 
    0, 
    DIVIDE(ClosedExplanationCount, TotalComplaints, 0)  // Safely divide
)

3)In Progress % = 
VAR InProgressCount = 
    CALCULATE(
        COUNT(Data[Complaint ID]), 
        Data[Company response to consumer] = "In progress"
    )
    
VAR TotalComplaints = COUNT(Data[Complaint ID])
VAR Result =
    IF(
        TotalComplaints = 0 || ISBLANK(TotalComplaints),
        0,
        DIVIDE(InProgressCount, TotalComplaints, 0)
    )
RETURN 
IF(ISFILTERED('date'[Year]) && ISBLANK(Result), 0, Result)

** REST OTHER DAX IS SAME AS ABOVE JUST CHANGE THE CALULATE FILTER DATA 

4)total complaints = COUNT(Data[Complaint ID])

5)PY COMPLAINTS = CALCULATE([total complaints],SAMEPERIODLASTYEAR('date'[Date]))

6)YOY Complaints% = DIVIDE([total complaints]-[PY COMPLAINTS],[PY COMPLAINTS],0)
