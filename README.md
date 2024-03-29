# Salary Data Analysis

## Abstract
The dataset was compiled by gathering information from various sources, such as surveys, job posting websites, and publicly accessible data. A total of 6,704 data points were collected. The dataset consisted of five variables: age, experience, job role, education level, and salary. The objective of this analysis is to find out how the above factor affect the salary an individual receives for the service he or she renders.

### Variables
- Age
- Gender
	- Male
	- Female
- Education Level 
	- High School
	- Bachelor’s
	- Master’s
	- PhD
- Job Title
	- Divisions
		- Accountant
		- Business
		- Customer Care 
		- Developer
		- Director
		- Engineer
		- Finance
		- HR
		- Managerial
		- Marketing 
		- Operations 
		- Sales
		- Science and Analytics

- Years of Experience 
	- Rank
		- Intern
		- Junior
		- Mid-level
		- Senior
		- Managerial	
		- Executive
- Salary
	- Salary-division
		- Low
		- Moderate
		- High


## Objective
The main focus of this analysis is to provide answers to the following questions;
1.	Is there a relationship between the education levels and the salary taken?
2.	Is there a relationship between the years of experience and the salary taken?
3.	Which department pays the most and the least and why?
4.	Who is taking the least and what's their demographics?
5.	Which gender is receiving the highest compensation and what are the reasons behind it?


## Analysis
1.	Is there a relationship between the education levels and the salary taken?
![All Segments Dashboard snapshot](https://github.com/LouisLiron/Project-1/assets/124049051/9dea03fa-d306-450c-b198-6b06bc20245e)

The provided image displays the average salary in various industries based on the educational attainment of individuals. It is evident from the graph that individuals with a PhD (representing the highest level of education) receive the highest salaries and individuals with High school certificate receive the lowest. The salaries received by individuals have been divided into three categories: high, moderate, and low. Now, let's examine which level of education dominates each of these three salary segments and derive some conclusions based on the data.


### High category:
![High](https://github.com/LouisLiron/Project-1/assets/124049051/80df36b2-c888-4109-a1b0-e3133085f2bc)

According to the presented image, individuals holding a PhD degree earn the highest salaries within the "High salary" category, followed by those with a Master’s degree. Bachelor's degree holders come next, while individuals with a High school education have the lowest salaries in this category.


### Moderate category:
![Moderate](https://github.com/LouisLiron/Project-1/assets/124049051/c857e3a2-8295-4582-b9cf-22e491c6f899)

Reiterating the information from the image, it is evident that PhD holders dominate the top position in terms of earning the highest salaries within the "Moderate" category. Conversely, individuals with a High school certificate hold the lowest position in this category.


### Low category:
![Low](https://github.com/LouisLiron/Project-1/assets/124049051/b3d0e536-fee1-4963-bdaf-f3ca63068245)

In this case, individuals with a Bachelor's degree take the lead in terms of earning the highest salaries, although it is notable that the difference between the top three categories is not substantial. Following Bachelor's degree holders, we have Master's degree holders, then PhD holders, and finally individuals with a High school education having the lowest salaries.

### Conclusion
Across all three categories, High school education consistently lags behind, while PhD holders dominate the first two categories and individuals with Bachelor's degrees lead in the last category (Low). It is fitting to conclude that having a higher education level, although not the sole determining factor, provides a solid foundation for receiving higher compensation for the services rendered.


2. Is there a relationship between the years of experience and the salary taken?
To facilitate analysis, the variable "Years of Experience" was segmented into smaller intervals. Now, let's delve directly into the findings.

![Picture3](https://github.com/LouisLiron/Project-1/assets/124049051/b9eb5afb-daee-4844-bfe6-ec9be5aca469)

Based on the doughnut chart analysis, it is evident that individuals holding the "Executive" rank receive the highest salaries. Following them are individuals in the "Managerial" rank, then the "Senior" rank, the "Mid-level" rank, the "Junior" rank, and finally the interns. The associated years for each rank are as follows:
- Executive: 30+ years
- Managerial: 23-30 years
- Senior: 15-22 years
- Mid-level: 7-14 years
- Junior: 1-6 years
- Intern: 0-0.5 years (indicates individuals who worked only for a couple of weeks)

### Conclusion
These findings clearly demonstrate that having a significant number of years of experience enhances your chances of receiving higher compensation for the services you render.


3.	Which division pays the most and the least and why?
![Picture2](https://github.com/LouisLiron/Project-1/assets/124049051/de32ecf5-db84-4b43-916c-fe012d349e44)

According to the presented chart, individuals in the "Director" division have the highest salaries, while those in the "Customer Care" division have the lowest. To understand the reasons behind this disparity, let's refer to another chart for further analysis.

![oK](https://github.com/LouisLiron/Project-1/assets/124049051/b3479af6-71b7-4d70-bd67-c22489b94981)

The chart above provides insights into the composition of the "Director" division, where individuals with Bachelor's, Master's, and PhD degrees are included. In total, there are 443 individuals in this division, out of which 247 hold a PhD degree. As previously established, PhD holders are known to receive high salaries, and their representation of 55.7% within the division significantly contributes to the overall higher salary figures. Additionally, there are 138 individuals with a Master's degree and 53 individuals with a Bachelor's degree, all of whom also receive high salaries.
On the other hand, the majority of individuals in the "Customer Care" division have High School and Bachelor's degrees. As mentioned earlier, these two education categories tend to have lower salary ranges. The following chart corroborates this observation.

![ok 2](https://github.com/LouisLiron/Project-1/assets/124049051/50b3e645-39a5-431c-928a-1f3fabb7ca5c)

### Conclusion
The highest salaries are earned by individuals in the "Director" Division, which comprises positions such as Directors, Operation Directors, CEOs, Marketing Directors, and similar roles. Conversely, the individuals in the "Customer Care" Division, which includes positions like Customer Care Representatives, Delivery Drivers, Customer Service Representatives, etc., receive comparatively lower salaries. The discrepancy in salary levels can be attributed to the level of education held by individuals in these divisions.



4.	Who is taking the least and what's their demographics?
From my analysis, I discovered that the individual taking the least salary has the following credentials;
	|Gender|Age|Education Level|Job Title|Divisions|Years of Experience|Rank|Salary|Salary Division|
	|--------|--------|--------|--------|--------|--------|--------|--------|--------|
	|Male|29|Bachelor’s|Junior Business Operations Analyst|Business|1.5|Junior|350|Low|
	
	


Analyzing the demographics of this individual, several observations can be made. Despite having an Education Level that is not at its lowest, the combination of his years of experience and job as a Junior Business Operations Analyst seems to hinder their prospects.


5.	Which gender is receiving the highest compensation and what are the reasons behind it?

|Row labels|Average  of Salary|Count of Personnel|
|--------|--------|--------|
|*Female*|10,8374|2993|
|PhD|160266|496|
|Master’s|122695|1068|
|Bachelor’s|89165|1198|
|High School|30368|231|
|*Male*|121396|3671|
|PhD|168711|837|
|Master’s|140061|790|
|Bachelor’s|98972|1823|
|High School|39381|185|

Based on the provided table, it can be observed that males tend to receive higher salaries. This can be attributed to the fact that males outnumber females in terms of holding PhD degrees. As established earlier, individuals with PhD degrees generally command higher salaries. While females lead in the number of Master's and High school degree holders as well, males particularly dominate in the Bachelor's degree category. The larger presence of PhD holders among males significantly contributes to higher average salary figures for males compared to females.

## Descriptive Analysis
Mean:
~~~SQL
SELECT 
    ROUND(AVG(Salary), 1) AS Mean 
FROM Salary_Data;
~~~
**Results**
|Mean|
|--------|
|115547.5|

The mean of 115547.5 suggests that, on average, the individuals in the Salary Dataset earn approximately $115,547.5. This value provides a measure of central tendency for the salaries in the dataset and can be useful in understanding the typical salary level.

Median:
~~~SQL
--Median of the dataset
SELECT TOP 1
    PERCENTILE_CONT(0.5) WITHIN GROUP (ORDER BY Salary) OVER() AS Median
FROM Salary_Data
~~~
**Results**
|Median|
|--------|
|115000|

The median value of 115,000 suggests that half of the individuals in the Salary Dataset earn less than 115,000, while the other half earn more than 115,000. It provides a measure of the central tendency that is not influenced by extreme values or outliers, making it useful for understanding the typical salary level.

Mode:
~~~SQL

--mode of the dataset
SELECT 
	Salary, 
	COUNT(*) AS Frequency
FROM Salary_Data
GROUP BY Salary
HAVING COUNT(*) = (
    SELECT MAX(Frequency)
    FROM (
        SELECT Salary, COUNT(*) AS Frequency
        FROM Salary_Data
        GROUP BY Salary
    ) AS Subquery
);
~~~
**Results**
|Salary|Frequency|
|--------|--------|
|140000|287|

The mode value of 140,000 indicates that this salary amount occurs most frequently in your dataset. Specifically, out of all the individuals in your dataset, 287 individuals have a salary of 140,000.

Skewness:
~~~SQL

--skewness of the dataset
SELECT 
    (SUM((Salary - Mean) * (Salary - Mean)) / (COUNT(*) * POWER(STDEV(Salary), 2))) AS Skewness
FROM 
    Salary_Data
CROSS JOIN (SELECT AVG(Salary) AS Mean FROM Salary_Data) AS Subquery;
~~~
**Results**
|Skewness|
|--------|
|0.999849939975993|

A skewness value of 0.999849939975993 suggests that the distribution of salaries in the dataset is positively skewed. Positive skewness means that the tail of the distribution extends towards higher values, indicating that there are more salaries towards the lower end of the scale and fewer salaries towards the higher end.

Kurtosis:
~~~SQL
SELECT 
    (SUM((Salary - Mean) * (Salary - Mean) * (Salary - Mean) * (Salary - Mean)) / (COUNT(*) * POWER(STDEV(Salary), 4))) - 3 AS Kurtosis
FROM 
    Salary_Data
CROSS JOIN (SELECT AVG(Salary) AS Mean FROM Salary_Data) AS Subquery;
~~~
**Results**
|Kurtosis|
|--------|
|-1.16690351743838|

A kurtosis value of -1.16690351743838 suggests that the distribution of salaries in the dataset has negative kurtosis. Negative kurtosis indicates that the distribution has lighter tails and a flatter peak compared to a normal distribution.

A negative kurtosis value means that the dataset has fewer extreme outliers or extreme values compared to a normal distribution. It indicates a relatively more dispersed or flat distribution of data.

## Overall Conclusion
Based on the dataset, it is evident that several factors, such as Education Level and Division or industry affiliation, significantly influence the amount of salary received by an individual. Achieving high scores in these areas is crucial to ensure a comfortable level of compensation. Thank you for looking at this project. Have a wonderful day!

## Dashboard
Access an interactive dashboard here; https://public.tableau.com/app/profile/louis.baddoo/viz/Salary_DataDashboard/Dashboard1

## Presentation Document
Also access a full presentation on this analysis here: https://bit.ly/472wQqC
