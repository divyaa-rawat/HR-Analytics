# HR Data Analytics


### Explore the Dashboard :https://app.powerbi.com/view?r=eyJrIjoiZGVmN2RjNjctNWU3MS00Y2YyLThiMDAtZDM0MzBjNGQ5MjYzIiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9

## Project overview

This dashboard serves as a valuable tool for the Human Resource Department, aiding in informed decision-making and gaining insights into employee behavior. It enables HR to understand employee preferences through various matrices, identifying areas for improvement. 

By analyzing sick leave percentages, the department can pinpoint opportunities to enhance productivity. In essence, it empowers HR to optimize workplace strategies and foster a more productive and employee-friendly environment.



### Steps followed 

#### Load Data:

- Import your attendance dataset from a CSV file into Power BI Desktop.
#### Transform Data:

- Clean and organize the data using Power Query Editor.
- Duplicate the query and name it "template."
- Select a specific sheet (e.g., Apr 2022) in the template.
- Use the first row as the header and adjust column names.

#### Unpivot Dates:

- Consolidate dates into a single column, excluding "Employee ID" and "Name," using the unpivot option.
#### Format Date Column:

- Rename the consolidated column as "Date" and convert it to a date format, eliminating text values.
#### Create Parameter:

- Establish a parameter for the April month sheet named "Worksheet."
#### Create Transformation Function:

- Transform the template query into a function named "GetData" to apply the transformation to all sheets.
#### Invoke Custom Column:

- Select the main query (Attendance Sheet) and add a column using the "Invoke Custom Column" option. Apply the "GetData" function to all sheets.
#### Load Data:

- Load the transformed data into Power BI.
#### Create Measures:
           *Total Working Days = var totaldays = COUNT('Final Data'[Date]) 
            var nonworkingdays = CALCULATE(count('Final Data'[Value]),
           'Final Data'[Value] in { "WO","HO"}) Return toaldays - nonworkingdays  
           
           *Present Days = var Presentdays = CALCULATE(count('Final Data'[Value]),
           'Final Data'[Value] = "P") return Presentdays + [WFH Count]

           *Presence % = DIVIDE([Present Days],[Total Working Days],0)

           *WFH Count = SUM('Final Data'[WFH Count])
          
           *SL Count = SUM('Final Data'[SL Count])

           *SL % = DIVIDE([SL Count],[Total Working Days],0)
#### Create Visuals:

Utilize cards to display Presence %, Work From Home %, and Sick Leave %.
Create table visualizations for Attendance Matrix Overview, Daily Attendance Overview, and Presence %, WFH %, SL % by weekdays.
Generate an Area Chart for the day-wise visualization of Presence %, WFH %, and Sick Leave %.


### Learnings from the project


* Understand P&L stuff, look at numbers, and figure out how things are going.

* Use special measurements (KPIs) to see how well we're doing in Finance, Sales, Marketing, and Supply Chain.

* Learn a lot about the consumer goods world, figuring out trends, what customers like, and how the industry works.

* Get better at talking and working with important people (stakeholder management).

* Pull out data easily using MySQL and Power Query, making sure all the right info is there.

* Use smart tricks with data (modeling and DAX), making it easier to understand and show.

* Make sure all the data is right in Excel, checking and double-checking.

* Make useful reports in Power BI, showing important stuff in a clear way for better decisions.



### Dashboard Overview

First View
![First View](https://github.com/divyaa-rawat/Project/assets/147628244/4fe77280-e815-43a7-8f45-5b9ce0b534d0)

Second View
![Second View ](https://github.com/divyaa-rawat/Project/assets/147628244/b584088d-5f54-48e1-b7c4-f91fce0b15cd)
