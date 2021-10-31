# Kickstarter Analysis

## Overview of Project
Louise is a playwright who is looking to uncover trends in the **Kickstarter** dataset, which includes data on a wide list of crowdfunding projects with their respective fundraising information, such as variables for the amount a play was aiming to fundraise (*goal*) versus how much it actually did (*pledged*), a categorical variable determining the outcome of the project's fundraising campaign, launch dates, and deadlines. Louise was looking to fundraise for her play, *Fever*, and while she has come close to her fundraising goal in a short time frame, she would now like to know how other plays fared with regards to their launch dates and their fundraising goals. 

## Analysis and Challenges

### Outcomes Based on Launch Date
First, Louise would like to understand the trends behind how well plays did with regards to their launch date. In particular, Louise will be looking at the *theater* category in the dataset. For this, we created a *Years* column that extracts the year from the *Data Created Conversion* column, which converts time data from the *launched_at* column into readable and understandable dates. For this, we use the `YEAR()` function. Then, we will create a Pivot Table that filters the **Kickstarter** dataset by the *Parent Category* and *Years* columns. This will allow Louise to look at theater play data by the year she would like to see. The rows of the Pivot Table will contain the *Date Created Conversion* column, and we will remove the automatically created *Quarters* option to visualize the data for every month of the year from January to December. The *outcomes* will be filtered on the columns of the Pivot Table by *successful*, *failed*, and *canceled* outcomes. 

<img width="330" alt="TheaterOutcomes_LaunchDate" src="https://user-images.githubusercontent.com/92702922/139589946-75310f4e-3cf0-4e82-82dc-7770f271f7d3.png">

Then, we created a line chart to visualize the number of theater plays that were successsful, failed, or canceled for each month in any given year. 

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/92702922/139591341-a334e5b9-7e21-4e9d-aeef-bbabde7354f5.png)

### Outcomes Based on Goals
Next, Louise would like to understand the association between fundraising outcomes depending on their fundraising goal. To do this, we create a new worksheet that includes several new columns: *goals*, *number successful*, *number failed*, *number canceled*, *total projects*, *percentage successful*, *percentage failed*, and *percentage canceled*. These are all derived from the original **Kickstarter** data. As their names suggest, these columns will help us understand and visualize both the number and percentage of successful, failed, and canceled projects. The *goals* column splits projects based on a range of goal amounts, from *Less than 1000* to *Greater than 50000*. 

<img width="117" alt="Screen Shot 2021-10-31 at 11 39 00 AM" src="https://user-images.githubusercontent.com/92702922/139593571-5a743cf3-ca77-4f0d-9477-a34cce5bd96b.png">

Here, we use the 'COUNTIFS()' function in excel to group projects based on their fundraising goal while taking a count for each *goal* category. From there, we take each outcome's share relative to the total number of projects. Finally, we create this line chart to visualize each fundraising project's outcome share relative to the total. 

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/92702922/139595084-a0dea88e-4a45-46f3-932a-287a76a02d2d.png)

### Challenges
Some potential challenges or difficulties that can arise in the analysis of this data can begin anywhere from cleaning the data, creating new variables/columns with new formulas, applying filters, and creating the adequate PivotTable and/or PivotChart. When one of these is mistakenly entered, the analysis results and visualization will likely result in a very erroneous interpretation. 

## Results

### Theater Outcomes by Launch Date
Now that we have performed our analysis for Louise, we arrive at a few conclusions: May seems to be the month that has the highest number of successful fundraising campaigns for theater plays, but also the highest number of failed projects. November seemed to have the lowest number of failed projects, while October recorded no canceled projects.

### Outcomes Based on Goals
Initally, we see that fundraising campaigns are more likely to be successful if their fundraising goal is relatively lower, particularly less than $5,000. However, we see that fundraising projects are also more likely to be successful when fundraising goals are roughly between $30,000 to $45,000, which may speak to particular projects that are renowned and have a sort of reputation effect that leads to successful crowdfunding. After this fundraising range, projects are again less likely to meet their fundraising goals, which may indicate goals that are deemed too excessive.

### Limitations and Recommendations
This dataset includes many variables that can help Louise understand and visualize crowdfunding for a variety of projects, whether those be in film, television, theater, etc. We were also able to derive new variables that would allow us to help Louise better understand these trends. A potential limitation of the data is the ambiguity of defining the variable for fundraising goal and comparing that to the amount that was pledged towards a particular project. For projects that don't reach their goal, are they still able to improvise and be executed? Likewise, is the outcome of a project reaching or not reaching their fundraising goal a proper indicator of whether a project is executed or not? The amount of canceled projects may help address this issue, but it seems that there is far too low of a number of these to tell us more about this data.

As for recommendations for additional visualizations, it may be useful to *both* filter the data by theater projects and split them by their fundraising goals. This will allow us to visualize two key points that are of interest to Louise as a playwright. Another suggestion would involve looking at the interval between fundraising launch dates and deadlines as a way to measure if these projects were successfully executed of not.
