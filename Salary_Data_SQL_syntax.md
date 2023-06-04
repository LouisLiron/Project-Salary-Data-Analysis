~~~SQL
--Is there a relationship between the education levels and the salary taken?
select 
  Education_Level as Education_Level,
  ROUND(AVG(Salary), 0) AS Salary_Taken
FROM 
  Salary_Data
GROUP BY [Education_Level]
ORDER BY 2 DESC
~~~
**Results**
|Education_Level|Salary_Taken|
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
