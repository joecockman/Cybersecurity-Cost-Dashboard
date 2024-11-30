# Cybersecurity-Cost-Dashboard
![Cybersecurity-Dashboard Preview](Cybersecurity-Dashboard.png)

I created this dashboard as part of my 12 week data analytics bootcamp. The goal was to create an interactive dashboard that users could use to estimate the cost  and implementation time of cybersecurity solutions for their business. 

For this project we partnered with KPMG, who gave us the 5 most common areas of cybersecurity weakness and the specific cybersecurity gaps within those areas. We then researched the current industry leading solutions for each gap and added the pricing and implementation time information.

For each cybersecurity gap we included a primary and alternative solution so that users could compare options.

We also included different options for different sized businesses. These were based on the following scale.

 - Small: 1-49 employees

 - Medium: 50-249 employees

 - Large: 250+ employees

## I have included visuals on the following variables:

- Matrix table displaying information
- Initial solution setup cost
- Annual solution cost
- Running summed totals
- Severity gauge

## I have also included filters on the page to help narrow your search. These include:

- 'Number of employees' search bar
- Cybersecurity area dropdown
- Cybersecurity gap dropdown
- Solution type toggle - primary or alternative solution

## I created the following measures that are used in many of the visuals:

- Company Sizing
- Filtered Average Annual Costs
- Filtered Average Initial Costs
- Filtered Average Monthly Costs
- Filtered Implementation Times
- Max Severity
- Severity Colour

## Please read on to find detailed explanations of how I put together different aspects of this dashboard:

# Number of Employees Search Bar

![Search Bar Preview](Screenshots/Number-of-Employees.png)

To create the search bar function I used a numeric range parameter ranging from 1 - 1000. I then created a slicer and added that parameter as the slicer field.

Next, I created a card (found in the top right of the dashboard) that will display the company size (small, medium  or large) depending on the number entered into the search bar.

I used a measure to achieve this functionality, the code is shown below.

Company Sizing:

```
Company Sizing = SWITCH(
TRUE(), 
SELECTEDVALUE(‘Number of Employees’[Number of Employees]) <= 49, “Small”,
SELECTEDVALUE(‘Number of Employees’[Number of Employees]) <= 249, “Medium”,
“Large”
)
```

This measure assessed the input to the search bar and returned 'Small', 'Medium' or 'Large' based on the rules established in the code.


