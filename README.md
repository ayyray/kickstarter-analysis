# Launch Date Success: Campaign Analysis
An analysis of kickstarter data for module 1 challenge

## Overview of the Project

### Purpose: 
In the challenge, “Launch Date Success: Campaign Analysis”, I assumed the role of an analyst tasked with determining if the launch date of different campaigns played a role in the success or failure of a campaigns funding goals being met. Through various analytical tests (which I will dive into), I sought out to find cross-tabular relationships in order to determine if indeed there was a relationship between the launch date (independent variable) of a campaign and its success (dependent variable) in reaching their funding goals.



### Background:
The inspiration for this analysis began with an individual (Louise) who had a campaign that came close to its fundraising goal in a short amount of time. It got her thinking, how have other campaigns done in terms of meeting their goals- depending on when they launched their campaign. From there I was given a data set [Kickstarter Data](https://github.com/ayyray/kickstarter-analysis/blob/main/Kickstarter_Challenge_1.xlsx). I took this data and conducted 2 statistical analyses that would help visualize and eventually help me come to a conclusion. With the assistance of Microsoft Excel, a massive data set of over 4,000 Kickstarter campaigns (4,113 to be exact), and a lot of filtering I began my analysis.

* The first “challenge” I conducted focused on determining which data was necessary and which was essentially dead weight, and then creating a pivot table and line chart to visualize how a campaign (specifically theater) fared in its funding success based off of when it was launched. The results are shown below:

![image](https://user-images.githubusercontent.com/96212660/148705996-3bca3296-eae8-4668-9264-e3ddb86593d2.png)


 * The second “challenge” dug a little deeper into defining the success of the campaigns through percentages. This was done through the use of the **COUNTIF()** functions and once again supported by a visualization (line chart) below:

![image](https://user-images.githubusercontent.com/96212660/148706010-a451ac18-9f46-493a-a8a9-f1b71aa36dca.png)


I finished it off by analyzing the data and creating an extensive and thorough analysis to come to a conclusion. 



## Analysis and Challenges

### Overview of Analysis:

#### Challenge 1 Analysis: 
Challenge 1 filtered the massive dataset into a smaller data set which made it a lot more practical and easier to work with. I knew I wanted to focus on finding a relationship between the independent variable (the launch date of the campaigns) and the dependent variable (the outcome-“success, failure, or cancellation” of the campaigns). Success was determined on whether an individual campaign met their campaign funding goals.

Through the filtering of the dataset, I was able to find more accurate and valuable relationships for my analysis. I found having more specific variables can show more specific trends and relationships.

One of the columns in the dataset provided a Unix timestamp of when a campaign was launched, using the **YEAR ()** function I converted the timestamp to a year. This conversion allowed me to provide a more accurate and less vague independent variable. When I created the pivot table, I was able to filter even further the independent variables from “years” to “months”.

![image](https://user-images.githubusercontent.com/96212660/148706110-07d9ef8a-bb5f-4647-89b6-571bdcdf512a.png)

![image](https://user-images.githubusercontent.com/96212660/148706680-8212258d-a2e8-4ef1-b5c6-362635b88fce.png)



I was able to not only filter the independent variable, but also the dependent variable (choosing only to show the outcomes that were necessary for my analysis) and the parent category. Instead of showing over 41 categories and then 41 subcategories, I filtered the data down from a “category and subcategory” into a “parent category”. This allowed me to focus on one specific category for my analysis: theater.

Filtering the data down and creating a pivot table gave a me a lot of secure data to begin an analysis of the relationship between the independent and dependent variable, but I required a visual to help support this data.

#### Challenge 1 Analysis of Data:
In challenge 1 displayed and measured success (y-axis) on a scale of 0-120 and the launch dates (x-axis) on a monthly range. The pivot table gave me an idea of peak success and failure (for example the month of May had the most successful month with 111 successful campaigns). It also provided me with a total number of campaigns and total number of successful/failed/canceled campaigns. While the pivot table allowed me to make concrete relational conclusions, I was not going to be sure until I could visualize it and see any potential trends. That is where the line chart comes in handy. The month of May was the most successful month for theater campaigns to launch and meet their funding goals. This was able to be seen on the line chart (and pivot table) with the highest spike on the Month of May. As I noted earlier, success was determined on whether or not the campaign met their campaign/funding goal. In the original data set, column [E] was labeled “pledged” and column [D] was labeled “goal”. If [E] > = [D], then the outcome was successful, However, if [E]  < [D] the campaign was labeled “failed”. 

In summary, challenge 1 focused on: 
- Filtering the data
- Determining the relationship between outcome and launch date
- Visualizing trends of variable relationship

#### Challenge 2 Analysis:
Once I had determined the relationship between launch date and campaign outcomes, I then wanted to figure out just how successful (or not successful) outcomes for Sub-Category “play” was (remember this for later). I now set out to figure out the percentage of success and failure (for each individuals’ campaign funding goal). In order to do this, I extracted what each campaigns funding goal was from the original data set, (but this time instead of filtering down to parent category “theater”, I filtered the data into subcategory “plays”. I broke down the goals into a specified range so I could better see just how relational campaign goal amounts affected outcomes. And found the percentage of successful/failed/canceled projects-all in a new sheet. Using the **COUNTIF()** function, I was able to populate my new sheet more efficiently. The results are included below.

![image](https://user-images.githubusercontent.com/96212660/147795345-01671d76-f668-4b8d-bb9c-ec86afb8f9b9.png)

My new sheet without any data looked like this. The COUNTIF() function allowed me to populate the sheet into the exact categories that I needed. I wanted every successful,canceled, and failed campaign outcome to be broken down based on how much their funding goal was. I have included some of the specific formulas below.

**- Cell (B1) Formula: =COUNTIFS('Kickstarter Data'!$F$:$F, "successful",'Kickstarter Data'!$D$:$D,"<1000",'Kickstarter Data'!$R$:$R,"plays")**

**- ('Kickstarter Data'!)** This pulls data from the original data sheet title "Kickstater Data"

**- ($F:$F)** This pulls data from column F

**- ("successful")** This pulls every project from column F that is "successful" 

**- ($D:$D, "<100")** This pulls every every project from column D that is less than $1000

**- ($R:$R, "plays")** This pulls every project from column R that is categorized as a play.

The end results filled cell (B1) with a tally of every project that met all the requirements from that formula and input it. The end result of utilizing the **COUNTIF()** function is shown below:

![image](https://user-images.githubusercontent.com/96212660/147795880-b594311a-a92f-4862-8aad-735be2110e6e.png)


The next step was finding the percentage of outcomes. I used the **SUM()** function to add up all the successful, all the failed, and all the canceled outcomes and created a new column labeled, "Total Projects). 


![image](https://user-images.githubusercontent.com/96212660/147796070-dafa0918-8261-44f2-bb38-1678f187505b.png)

The **SUM()** worked horizontally. For example, in order to fill cell (E2), I used the formula **=SUM(B2:D2)** and got 186. From there I was able to move on to finding percentages.

![image](https://user-images.githubusercontent.com/96212660/147796167-4bc72aa3-d8c3-4c5a-b332-5723c97752b6.png)

Finding percentages was as simple as dividing the # of part by the total. For example, in order to fill cell (F2), I simply used =(B2/E2). In the end my complete new sheet looked like this:


![image](https://user-images.githubusercontent.com/96212660/147796255-8263fa32-223c-4ec8-8015-a51d3d02a01d.png)


This sheet laid out just the information I needed in order to determine the percentage of outcomes for projects based on how much money they wanted to raise. Similar to challenge 1, I needed to visualize in order to determine trends. I created a line chart using the data as shown below.

![goals](Outcomes_vs_Goals.png)

#### Challenge 2 Analysis of Data:
Based on the results of the visualization and data for Challenge 2, I noticed that there is an inverse relationship between the percentage of success and the percentage of failure when it came to campaign outcomes. This had to do with the fact that there were no “canceled” outcomes under sub-category “plays”. I also noticed that goals that were <1000 between goals < = 4999 were most likely to be successful.

There was a total of 1,047 total project for this challenge, filtering the. Subcategory under “plays”.

According to the dataset/pivot table, campaigns that had a goal of <1000: 141 out of 186 total were successful. Campaigns who goal was between 1000-4999: 388 out of 534 were successful. Combining those 2 ranges- out of 720 total projects, 529 were successful coming out to a 73% success rate within the ranges, 76% of all successful campaigns, and 50% of all projects.


### Challenges and Difficulties:

Although I started this project with an idea of what I wanted to figure out, the massive amount of data set out in front of me was overwhelming at first. It was easy to feel lost at times, especially if I was not logging down my process and intentions periodically. In order to combat this, I made sure I knew what each column of data represented in the analysis. For example- when I was trying to figure out the percentage of outcomes based on goals- the use of the COUNTIF () function was helpful in separating such a massive amount of data into whatever categorization that I wanted. Without that step I would have been looking at a giant dataset of 1047 projects trying to figure out which column I needed to move the data from, and which was just dead weight. Another challenge was knowing which variable went where during the creation of my charts and graphs. But the use of pivot tables was crucial in aiding in creating these visual aids. Knowing which variable is going to go on which axis, which variable will be measured, etc. The use of pivot tables allowed me to move variables around more fluid so I could better determine what relationships I wanted to cross analyze. The challenges I faced in this project stemmed from an excess amount of data. In order to overcome these difficulties, I slowed down, logged my progress, utilized the **COUNTIF ()** and pivot tables, and always kept my objectives in sight.

Another challenge I faced was finding relational value between parts of challenge 1 and challenge 2. In challenge 1, the dataset was filtered under the Parent Category “theater”. However, challenge 2 the data was filtered under subcategory “plays”. I was able to differentiate the purpose of each challenge as an individual relational test, but it made it a little bit harder to create an all-inclusive conclusion combining the data I had from both challenges

## Results

### Conclusions for Theater Outcomes by Launch Date:

#### Conclusion 1:
May was the most successful month in terms of a campaign meeting their funding goals. If I was to look at this data, I would recommend a Kickstarter campaign trying to launch their campaign in May. If May does not work, I would recommend trying to launch the campaign anytime between May or June. The rate of success in these months made up 26% of all the successful projects, and 16% of all projects. Those numbers might not be as impressive or assuring as one might hope, but it does make up the biggest spread in terms of success-failure through the whole year. With the highest percentage of success (May: 66% and June: 65%).![image]
 
#### Conclusion 2:
December held the highest likely hood of campaign failure. Out of the 12 months, 10 of them stayed within the 30-38% of failure, but the month of December had a spike of 46%. Although that was the month with the fewest amount of campaign launches, it still proves to be the least fruitful.

### Conclusion for Outcomes Based on Goals:

#### Conclusion:
As I stated earlier in my analysis, goals that were <1000 between goals < = 4999 (or in other words 0-4999) were most likely to be successful. Combining those 2 ranges- out of 720 total projects, 529 were successful coming out to a 73% success rate within the ranges, 76% of all successful campaigns, and 50% of all projects. I would conclude that if a campaign wanted to maximize their percentage of success by meeting their campaign funding goals that they should keep their goals somewhere between 1-4999.

### Summary of Limitations and Recommendations:

#### Limitations:
A couple of limitations I recognized from the data set were:

1.	I would like to have seen how much money was spent on the campaign. The whole point of conducting this analysis with this data set was to determine, “how different campaigns fared in relation to their launch date and funding goals.” We know how much money they raised but I want to know how aggressively they campaigned. I believe that money is a good indicator of how aggressive or not each Kickstarter was in promoting their campaigns. In order to raise money, you will need to spend money on ads, exposure, development plans, etc.

2.	The range for campaigns launch date for this data set is extremely massive. It ranges from 2010 all the way through 2017. I think there should be a range limitation to better accurately analyze this data. A lot can and has changed in those 8 years and I think having a small range of say 3-5 years (2013-2017) could prove to be a little more accurate.

3.	Branching off “how much money was spent on the campaign”, I would like to see how much money has gone into the project. Not just the campaign side but total production/project value. I think this would be beneficial in analyzing investors willingness to donate or invest in a campaign project that is more expensive or less expensive.

#### Recommendations:
1. I believe having a table or a graph that focused on the duration of the campaign would be beneficial in providing a visual of success based on duration of campaign. I would use the Unix Timestamp as my duration variable. I believe this would be a great addition in that it would be able to further pinpoint which months were most fruitful in launch success.

2. Another table that would be nice to have is a graph that shows the relationship between backer count and average donations. I would include this because it would help in creating a business plan when figuring out what average donations look like. It would also be helpful to highlight outliers of BIG donation amounts.

3. The third and final recommended table I would like to see is Outcomes Based on Goals but with a different category. In challenge 1, the dataset was filtered under the Parent Category “theater”. In challenge 2 the data was filtered under subcategory “plays”. I would like to either continue using the same filtered data from challenge 1 and apply it to the same analysis from challenge 2 or vice versa. 




![goals](Outcomes_vs_Goals.png)

![date](Theater_Outcomes_vs_Launch.png)
