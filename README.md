# School District Analysis 

## Overview 

prepare an analysis of all standardized test data for analysis, reporting, and presentation to provide insights on performance trends and patterns. These insights are to inform discussions and decisions at the school and district level. analyze data on student funding and students' standardized test scores. given data on math and reading scores, as well as, other various information on the schools they attend. task is to aggregate the data and showcase trends in school performance. This data will assist the school board and superintendent in making decisions regarding the school budgets and priorities.

A city school district wanted to have an analysis performed on standardized testing data retrieved from 15 different schools within that district. Two datasets were provided, one containing data about each school's budget, school type, and school size; the other containing data about the students, what school they were attending, grade, reading scores, and math scores. By merging the two datasets into one, an analysis was able to be performed that would showcase trends in school performance relative to each school's allotted budgets. This type of analysis can help the school district make decisions about whether student funding and/or the school's budget should be increased/decreased for the following year. 

## Purpose

Following the results of the this analysis, the school board wanted to have the school district analysis repeated due to reports of academic dishonesty occurring at Thomas High School. The evidence found showed academic dishonesty for the reading and math grades at the ninth grade level. Even though it is not known how much dishonesty actually took place, the school board wanted to make sure that the state-testing standards were not drastically altered by Thomas High School's ninth grade math and reading scores. In order to evaluate the school board's concerns, it was asked that I remove these scores from Thomas High School's, ninth grade class, and then present the findings from both analysis' and compare the results. 

## Resources 

* Data Source: schools_complete.csv, students_complete.csv
* Software: Python 3.9.12, Anaconda 4.13.0 (Pandas Library & Jupyter Notebook)

## The Data 

First, the two datasets were merged together by looking for a common denominator found in both datasets, which was "school_name". By merging the datasets together into one dataframe, I was able to perform subsequent mathematical calculations to identify and analyze trends that incorporated student math and reading scores, with each school's size and budget amounts. 

(pic of merged code)

Using this new dataframe, I was able to create a summarized table that was able to be broken down into various ways. A couple examples of how the data could be broken down, are as follows: analyzing test scores based on the type of school (Charter or District), budget per student, passing percentages per school, score averages per grade level, or which schools had the highest or lowest performing student scores. 

In order to remove the data for the ninth graders from Thomas High School, I had to use the loc method to replace the math and reading scores within the dataset to "NaN", meaning "Not a number". By placing "NaN" in place of the math and reading scores, the rest of the information within that row for that student would not be removed, and avoids the issue of placing a zero as the score, which would impact any arithmetic calculations down the line. This method allowed me to specify where I wanted to change the data without corrupting the rest of the data received from Thomas High School, for the grades, 10th through 12th. 

(pic of loc method)

## Results

Upon running both analyses, removing the math and reading scores for ninth graders at Thomas High School, had little to no effect on the overall analysis. 

* Effect on District Summary: 

(pic of old & new district summary)

By looking at the example shown above for the original vs. the updated district summary: 

	* "Average Math Score" went down by -0.1 points, and "Average Reading Score" stayed the same.
	* "% Passing Math" went down by -0.2%, "% Passing Reading" went down by -0.3%, and "% Overall Passing" went down by -0.1%.



* Effect on School Summary: The only effect was represented in the minute differences within the row for "Thomas High School", but other school data was not effected at all. 

* Thomas High School Performance relative to other schools: Again, removing the scores from the 9th grade class had little to no effect on this school's performance relative to other schools. 

(pic of old and new school summary) 

By looking at the example shown above for the original vs. the updated school summary:
	
	* "Average Math Score" went down by -0.1 points, and "Average Reading Score" went up 0.05 points.
	* "% Passing Math" went down by -0.1%, "% Passing Reading" went down by -0.2%, and "% Overall Passing" went down by -0.3%.

* Replacing the math and reading scores by grade did not make a difference overall the schools.
* Replacing the math and reading scores did not effect the scores that were separated by school size, except for the "Medium(1000-1999)" bin group when expressed as a float data type, but upon formatting, there was no difference between the two analyses.
* Replacing the math and reading scores by school spending only made a difference in the the row "$631-645", because this was the row that Thomas High School scores were applied to based on their total budget amount. 

(pic of old spending summary df and new spending summary df)

* Replacing the math and reading scores by school type only had a small effect on the averages and percentages in the "Charter" school group, but again, the effect was so minimal, that when formatting changes were made, there was no effect at all to either school type. 

(pic of old type summary df and new one showing percentage/formatting line/newly formatted type_summarydf) 











