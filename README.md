# School_District_Analysis

## Project Overview
### Purpose

Analyze school district data provided in a spreadsheet using Jupyter Notebook with Python, Pandas Library and Numpy library.
The School Board would like to understand various performance metrics of different schools. We did an initial analysis of the data and provided Maria with key performance metrics.

Even though the School Board is pleased with the analysis that was done, but it notified Maria and her supervisor that there are some discrepancies about the numbers, specifically for 9th grader data in Thomas High School.  In order to uphold the state testing standards, the School Board has requested Maria to take another look. Maria wanted us to replace the 9th graders Math and Reading scores to NaN(Not a Number) and re-do the whole analysis with the new student count (removing 9th graders data). She also wanted us to find how this change impacts various metrices.

### Resources
	• Data Source: schools_complete.csv
	• Data Source: students_complete.csv
	• Sofware: Jupyter Notebook 6.3.0
	• Library: Pandas
	• Library: Numpy
	
	
## Analysis of Results

### Impact on District Analysis

District Analysis - Original 
![image](https://user-images.githubusercontent.com/3753839/165873945-d4ac9c73-8ec6-44a6-8ead-ad31631d8cf7.png)


District Analysis- Updated  
![image](https://user-images.githubusercontent.com/3753839/165873952-7e37163b-bb82-425a-9e6a-8bac47431dbe.png)



Once the 9th graders data from Thomas High School was updated to NaN, basically voiding math and reading scores of 461 student, it did not affect the district analysis much. If you see the above data most of the metrices reduced by approx 0.2 percentage. The total number of student is 39,170 and we removed only 461 student's data. So that is 1.17% removed from the total which is way we don't see a significant impact to the district metrices.


### Impact on the School Summary 

School Summary - Original
![image](https://user-images.githubusercontent.com/3753839/165874156-3f3d82ef-a8da-462b-8c95-a086d319bccf.png)

Updated - Keeping 9th graders in Thomas high School.
![image](https://user-images.githubusercontent.com/3753839/165874176-b3d2018d-29ee-47b3-ab19-d76b6e6e6717.png)


Updated - Removing 9th graders in Thomas high School.
![image](https://user-images.githubusercontent.com/3753839/165874188-66c86e98-0c0b-49d6-bcf4-242ac463812b.png)



The School Summary was derived 2 times.
* 1st time  - After the 9th grader's math and reading scores were replaced with NaN, when we take the passing math and reading scores, we are excluding the rows that have NaNs as values because we are saying 
(school_data_complete_df["math_score"] >= 70)] or (school_data_complete_df["reading_score"] >= 70). But when we calculate the percentage we consider all the students for total counts which is considered in the denominator of the equation. So the final outcome is reducing drastically as we see in the % metrices above. We have the overall passing % drop from 91% to 65%.
* 2nd time  - However when we recalculate the School Summary removing the 9th graders altogether, meaning we consider new student count including only the 10-12 th graders, then the Overall passing percentages and other percentages shows considerable less reduction from the original value as shown below. The overall passing % reduced only 0.31% from the original.




### Thomas High School Performance to other schools

#### Top Schools

Top Schools - Original 
![image](https://user-images.githubusercontent.com/3753839/165874291-737a322a-ba68-4497-b346-7ac820c07d6c.png)


Top Schools - Updated 

Pic1: Removal scenario

![image](https://user-images.githubusercontent.com/3753839/165874305-65dc8e7d-ac48-40df-b09c-6be81d481398.png)



Pic2: Replacement Scenario
![image](https://user-images.githubusercontent.com/3753839/165875402-0294a3da-475d-4988-889f-28d1c682b993.png)


In the original ranking if we see Thomas High School is in the 2nd rank from top with an overall passing % of 90.94%.
Now there are 2 situations here
		* We replaced the 9th graders score by NaN and then determined the school summary DataFrame where we include all the students including 9th grader in total count for calculating percentages. This scenario will put the ranking for Thomas High School way below in the 8th with Overall Passing % as 65% as shown above in Pic2
		* We removed the 9th graders rows altogether and then determined the school summary DataFrame where we include only the 10-12th students  in total count for calculating percentages. This scenario will put the ranking for Thomas High School back to 2nd rank with Overall Passing 90.63% as shown above in Pic1. Overall impact was not much in this way of re-calculation.

In this challenge the place where we executed the Top School logic was considering 10-12th graders only for Thomas High School. That's why the impact was not noticed much as mentioned above. 
	

#### Bottom Schools

Bottom Schools - Original 
![image](https://user-images.githubusercontent.com/3753839/165875549-600b7ac4-2c4c-48a7-8568-7bb2174922ad.png)



Bottom Schools - Updated 
![image](https://user-images.githubusercontent.com/3753839/165875562-7fb6a76b-2289-4be3-934d-1093af110e72.png)



As we can see from the above snapshot, the ranking of the bottom schools was not affected as the updates were only made for Thomas High School.



### Impact on Math and Reading Scores by Grade

Math Scores - Original                                                                                                                                              

![image](https://user-images.githubusercontent.com/3753839/165874606-b5694b99-291a-4b91-89f0-c86dd3cf6d04.png)   


Math Scores - Updated

![image](https://user-images.githubusercontent.com/3753839/165874610-9956e7dc-391f-4ad6-b483-1a1d5a4420d5.png)




Reading Scores - Original

![image](https://user-images.githubusercontent.com/3753839/165874623-baf5f5de-2792-4e62-8549-004a2b6522b3.png)


Reading Scores - Updated

![image](https://user-images.githubusercontent.com/3753839/165874632-9db9a752-3f71-4727-8d2f-c55356d210cb.png)

	
Above snapshot is for DataFrames for Math and Reading which shows how the scores were replaced for 9th graders only for Thomas High School.



### Impact on Scores by School Spending

Original

![image](https://user-images.githubusercontent.com/3753839/165874661-df6a3269-5850-4745-926c-d7eb9ce27dce.png)


Updated

![image](https://user-images.githubusercontent.com/3753839/165874673-1eb93344-4286-4bd9-86a5-a339c1b54967.png)


The Per student Budget for Thomas High School is $638. And as we have made updates to records of that school, only the Budget range of $631- 645 is showing a difference here. However the percentage changes are very minimal a reduction of less than 0.1% in the Overall Passing %.


### Impact on Scores by School Size

Original

![image](https://user-images.githubusercontent.com/3753839/165875821-dc48cb08-c8e3-4583-aa72-0f8ef18c7373.png)


Updated

![image](https://user-images.githubusercontent.com/3753839/165875837-667a88ad-e8da-4515-be92-4771523ca108.png)


	
Thomas High School has 1635 students in total which falls in the range Medium (1000-1999). Also because we changed data only for Thomas High School for 9th graders, the impact can be seen only in this range. The change seen is however 0.1% reduction in overall passing %.


### Impact on Scores by School Type

Original

![image](https://user-images.githubusercontent.com/3753839/165876036-a99838a9-4513-4ffb-989e-9e28c73295cf.png)



Updated

![image](https://user-images.githubusercontent.com/3753839/165874763-9a5996e6-d0d6-4f58-9dfa-d89d09a5f40d.png)
	
Thomas High School is a Charter type school, so if we see the above metrics, only for Charter School type there is a slight change in Overall passing % like less than 0.1% .  



## Summary
### Summarizing the above analysis  

* School Summary considering Replacing 9th grader's data, it impacts the math and reading passing % by approx 28% percentage. Overall passing % is also drastically reduced from 91% to 65%.
* School Summary considering Removing 9th grader's data, considering only 10-12th graders data, it impacts the math and reading passing % by less than 0.5 percentage. Overall impact is very minimal 0.31% reduction.
* Top School Ranking - There was no change to ranking for Thomas High School as the calculation was done based off of 10-12th graders scores. Impact was only on the passing % which was less than 0.5%.
* Scores by School Size and School Type  - The changes were seen on the bands which included Thomas High School in considered for example Medium (1000-2000) grouping or Charter grouping and for all scores the impact was by less than 0.1 percentage because the starting dataFrame is "per_school_summary_df" which is calculated with only 10-12th graders data.

