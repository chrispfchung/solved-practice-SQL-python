*Challenge*: <https://www.hackerrank.com/challenges/weather-observation-station-20/problem>

*Problem*: Find the median value of the Northern Latitudes.

*Solution*:

set @rowindex := -1;

SELECT ROUND(AVG(s.l), 4) FROM
(SELECT @rowindex := @rowindex + 1 as rowindex, station.lat_n as l
 FROM STATION
 ORDER BY station.lat_n) as s
 WHERE
 s.rowindex IN (CEIL(@rowindex/2), FLOOR(@rowindex/2));

 *Explanation*:

 First I set the @rowindex to -1. I want to start my index off at 0 when I begin incrementing.
 Then I enumerate rowindex and the northern latitude values (lat_n) and sort them. My goal is to find the value in the middle. In the WHERE clause, I want the indexes that are in the center. In the case that the table is even, I'm going to round down the center value and round up the center value and calculate the average so that I have the value just in the center, rounded up to 4 decimal points.

 *Main Guidance*:
 <https://www.eversql.com/how-to-calculate-median-value-in-mysql-using-a-simple-sql-query/>
