# School District Analysis 

## Overview 

  A city school district wanted to have an analysis performed on standardized testing data retrieved from 15 different schools within that district. Two datasets were provided, one containing data about each school's budget, school type, and school size; the other containing data about the students, what school they were attending, grade, reading scores, and math scores. By merging the two datasets into one, an analysis was able to be performed that would showcase trends in school performance relative to each school's allotted budgets. This type of analysis can help the school district make decisions about whether student funding and/or the school's budget should be increased/decreased for the following year. 

## Purpose

  Following the results of the this analysis, the school board wanted to have the school district analysis repeated due to reports of academic dishonesty occurring at Thomas High School. The evidence found showed academic dishonesty for the reading and math grades at the ninth grade level. Even though it is not known how much dishonesty actually took place, the school board wanted to make sure that the state-testing standards were not drastically altered by Thomas High School's ninth grade math and reading scores. In order to evaluate the school board's concerns, it was asked that I remove these scores from Thomas High School's, ninth grade class, and then present the findings from both analysis' and compare the results. 

## Resources 

* Data Source: schools_complete.csv, students_complete.csv
* Software: Python 3.9.12, Anaconda 4.13.0 (Pandas Library & Jupyter Notebook)

## The Data 

  First, the two datasets were merged together by looking for a common denominator found in both datasets, which was "school_name". By merging the datasets together into one dataframe, I was able to perform subsequent mathematical calculations to identify and analyze trends that incorporated student math and reading scores, with each school's size and budget amounts. An example of how I was able to merge schools_complete.csv (=school_data_df) and students_complete.csv(=student_data_df) files into one dataset(=school_data_complete_df), is provided below.
  
![merged_df](https://user-images.githubusercontent.com/104864579/178060550-e758a84e-4c3b-49b9-b739-f78c9074f0d4.png)

  Using this new dataframe, I was able to create a summarized table that was able to be broken down into various ways. A couple examples of how the data could be broken down, are as follows: analyzing test scores based on the type of school (Charter or District), budget per student, passing percentages per school, score averages per grade level, or which schools had the highest or lowest performing student scores. 

  In order to remove the data for the ninth graders from Thomas High School, I had to use the loc method to replace the math and reading scores within the dataset to "NaN", meaning "Not a number". By placing "NaN" in place of the math and reading scores, the rest of the information within that row for that student would not be removed, and avoids the issue of placing a zero as the score, which would impact any arithmetic calculations down the line. This method allowed me to specify where I wanted to change the data without corrupting the rest of the data received from Thomas High School, for the grades, 10th through 12th. As shown below, is an example of how I used the loc method to select all the reading scores and math scores for the 9th graders at Thomas High School, and replaced the scores with NaN. 
  
![loc_method_NaN](https://user-images.githubusercontent.com/104864579/178060209-f9b074c3-96b3-4c39-8313-0dc67d9a8b47.png)

## Results

  Upon running both analyses, removing the math and reading scores for ninth graders at Thomas High School, had little to no effect on the overall analysis. 

* Effect on District Summary: 

![old_district_summary](https://user-images.githubusercontent.com/104864579/178059560-3cd90368-f677-4a97-9763-bc59454cf548.png)

![new_district_summary](https://user-images.githubusercontent.com/104864579/178059581-744396ad-cde3-4899-ba95-c03919aaf633.png)

 By looking at the example shown above for the original vs. the updated district summary: 

   * "Average Math Score" went down by -0.1 points, and "Average Reading Score" stayed the same.
   * "% Passing Math" went down by -0.2%, "% Passing Reading" went down by -0.3%, and "% Overall Passing" went down by -0.1%.

* Effect on School Summary: The only effect was represented in the minute, or minimal, differences within the row for "Thomas High School", but other school data was not effected at all. 

* Thomas High School Performance relative to other schools: Again, removing the scores from the 9th grade class had little to no effect on this school's performance relative to other schools. 

![old_school_summary](https://user-images.githubusercontent.com/104864579/178059687-68650ed6-0d55-44ba-b39d-e875df44229f.png)

![new_school_summary](https://user-images.githubusercontent.com/104864579/178059724-555a2512-66c2-4a2e-ad63-cda1afd02fda.png)

 By looking at the example shown above for the original vs. the updated school summary:
	
   * "Average Math Score" went down by -0.1 points, and "Average Reading Score" went up 0.05 points.
   * "% Passing Math" went down by -0.1%, "% Passing Reading" went down by -0.2%, and "% Overall Passing" went down by -0.3%.

* Replacing the math and reading scores by grade did not make a difference overall the schools.
* Replacing the math and reading scores did not effect the scores that were separated by school size, except for the "Medium(1000-1999)" bin group when expressed as a float data type, but upon formatting, there was no difference between the two analyses.
* Replacing the math and reading scores by school spending only made a difference in the the row "$631-645", because this was the row that Thomas High School scores were applied to based on their total budget amount. An example of the original analysis spending summary(1st image) and the updated analysis(2nd image) is shown below.

![old_spending_summary](https://user-images.githubusercontent.com/104864579/178062086-17872da7-d5e0-4193-8858-f67ebd5334db.png)

![new_spending_summary](https://user-images.githubusercontent.com/104864579/178061751-edc48d8a-ad6e-4df6-827f-ecb2216cbbcf.png)

* Replacing the math and reading scores by school type only had a small effect on the averages and percentages in the "Charter" school group, but again, the effect was so minimal, that when formatting changes were made, there was no effect at all to either school type. As shown below, an example of how there was not much difference between the Charter scores in the original analysis(1st image) and the Charter scores in the updated analyis(2nd image).

![old_school_type_summary](https://user-images.githubusercontent.com/104864579/178059835-95f8fbb5-05ab-4dbe-a333-08bc9fc7910a.png)

![new_school_type_summary](https://user-images.githubusercontent.com/104864579/178059847-fce6a490-8340-40e9-9046-23b67e43db84.png)











