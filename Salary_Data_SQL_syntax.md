~~~SQL
--Is there a relationship between the education levels and the salary taken?
select 
  Education_Level as Education_Level,
  ROUND(AVG(Salary), 0) AS Average_salary_Taken
FROM 
  Salary_Data
GROUP BY [Education_Level]
ORDER BY 2 DESC
~~~
**Results**
|Education_Level|Average_salary_Taken|
|--------|--------|
|PhD|165651|
|Master's|130078|
|Bachelor's|95083|
|High School|34376|

~~~SQL
--Is there a relationship between the years of experience and the salary taken?
select 
  Rank as Years_of_Experience,
  ROUND(AVG(Salary), 0) AS Salary_Taken
FROM 
  Salary_Data as sd
GROUP BY Rank
ORDER BY 2 DESC
~~~
**Results**
|Years_of_Experience|Salary_Taken|
|--------|--------|
|Executive|190668|
|Managerial|189609|
|Senior|179977|
|Mid-level|141537|
|Junior|76626|
|Intern|30444|

~~~SQL
--Which department pays the most and the least?
select 
  Divisions as Divisions,
  ROUND(AVG(Salary), 0) AS Salary_Taken
FROM 
  Salary_Data as sd
GROUP BY Divisions
ORDER BY 2 DESC
~~~
**Results**
|Divisions|Salary_Taken|
|--------|--------|
|Director|155790|
|Science and Analytics|145902|
|Engineering|131933|
|Managerial|131058|
|Finance|88475|
|Operations|81500|
|Developer|79378|
|Business|78343|
|HR|74583|
|Marketing|69868|
|Accountant|62000|
|Sales|35337|
|Customer Care|26479|

~~~SQL
--Who is taking the least and what's their demographics?
SELECT *
FROM 
  Salary_Data AS sd
WHERE Salary = 
	(SELECT 
		MIN(Salary) AS Least_Salary
	FROM Salary_Data)
  ~~~
  **Results**
  |Age|Gender|Education_Level|Job Title|Divisions|Years of Experience|Rank|Salary|Salary_division|
  |--------|--------|--------|--------|--------|--------|--------|---------|--------|
|29|Male|Bachelor's|Junior Business Operations Analyst|Business|1.5|Junior|350|Low|

~~~SQL
SELECT 
  Gender, 
  ROUND(AVG(Salary), 0) AS Avg_Salary
FROM 
  Salary_Data
GROUP BY Gender
ORDER BY 2 DESC
~~~
**Results**
|Gender|Avg_Salary|
|--------|--------|
|Male|121396|
|Female|108374|

~~~SQL
 --which education level has the highest number of certificate holders
 SELECT 
  Education_Level AS Education_Level, 
  COUNT(*) AS Count_of_Holders
FROM 
  Salary_Data as sd
GROUP BY Education_Level
ORDER BY 2 DESC
~~~
**Results**
|Education_Level|Count_of_Holders|
|--------|--------|
|Bachelor's|3021|
|Master's|1858|
|PhD|1369|
|High School|416|

~~~SQL
--Looking at the various divisions with a few descriptive stats
SELECT DISTINCT
    Divisions AS Divisions, 
    AVG(Salary) OVER(PARTITION BY Divisions) AS Division_avg,
    MIN(Salary) OVER(PARTITION BY Divisions) AS Division_min,
    MAX(Salary) OVER(PARTITION BY Divisions) AS Division_max
FROM 
    Salary_Data AS sd
ORDER BY 2 DESC
~~~
**Results**
|Divisions|Division_avg|Division_min|Division_max|
|--------|--------|--------|--------|
|Director|155790|70000|250000|
|Science and Analytics|145902|35000|240000|
|Engineering|131933|40000|210000|
|Managerial|131058|579|250000|
|Finance|88475|40000|200000|
|Operations|81500|35000|190000|
|Developer|79378|550|178284|
|Business|78343|350|170000|
|HR|74583|500|180000|
|Marketing|69868|35000|160000|
|Accountant|62000|35000|95000|
|Sales|35337|25000|160000|
|Customer Care|26479|25000|45000|

~~~SQL
--Looking at education Level and a few descriptive stats
SELECT DISTINCT
    Education_Level AS Education_level, 
    AVG(Salary) OVER(PARTITION BY Education_Level) AS Education_level_avg,
    MIN(Salary) OVER(PARTITION BY Education_Level) AS Education_level_min,
    MAX(Salary) OVER(PARTITION BY Education_Level) AS Education_level_max
FROM 
    Salary_Data AS sd
ORDER BY 2 DESC
~~~
**Results**
|Education_level|Education_level_avg|Education_level_min|Education_level_max|
|--------|--------|--------|--------|
|PhD|165651|579|250000|
|Master's|130078|32000|228000|
|Bachelor's|95083|350|250000|
|High School|34376|25000|165919|

~~~SQL
--displaying the gender and a few descriptive stats
SELECT DISTINCT
    Gender AS Gender,
    PERCENTILE_CONT(0.25) WITHIN GROUP (ORDER BY Salary) OVER (PARTITION BY Gender) AS Q1_Salary,
    PERCENTILE_CONT(0.50) WITHIN GROUP (ORDER BY Salary) OVER (PARTITION BY Gender) AS Median_Salary,
    PERCENTILE_CONT(0.75) WITHIN GROUP (ORDER BY Salary) OVER (PARTITION BY Gender) AS Q3_Salary
FROM 
    Salary_Data AS sd
ORDER BY 3 DESC
~~~
**Results**
|Gender|Q1_Salary|Median_Salary|Q3_Salary|
|--------|--------|--------|--------|
|Male|75000|120000|170000|
|Female|60000|105000|150000|

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
