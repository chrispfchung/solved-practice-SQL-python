**Challenge:** <https://www.hackerrank.com/challenges/full-score/problem>

**Problem:** Julia just finished conducting a coding contest, and she needs your help assembling the leaderboard! Write a query to print the respective hacker_id and name of hackers who achieved full scores for more than one challenge. Order your output in descending order by the total number of challenges in which the hacker earned a full score. If more than one hacker received full scores in same number of challenges, then sort them by ascending hacker_id.


Since there are four tables I wanted to join the tables together so that I could pick out what I wanted. It was helpful to visualize each step by selecting * from the beginning until I reached the last few queries using WHERE/GROUP BY/HAVING/ORDER BY. It was also helpful to read over the question to understand exactly what Julia, the client, wants. I learned that the tables needed to be joined first before operating on them. I learned that there doesn't need to be a ton of parentheses to separate the queries. I learned that you could combine WHERE conditionals. I learned that it's okay to rename everything to make typing easier.
I learned that you could group by 2 things which should match the final select that is what you want to query, hacker_id and hacker_name. Great code challenge.

*JOIN TABLES* 
SELECT h.hacker_id, h.name
FROM submissions s
INNER JOIN hackers h
ON s.hacker_id = h.hacker_id

INNER JOIN challenges c
ON c.challenge_id = s.challenge_id

INNER JOIN difficulty d
ON c.difficulty_level = d.difficulty_level

*SPECIFY CONDITIONS*
WHERE s.score = d.score and d.difficulty_level = c.difficulty_level

*Total and Group by hacker_id and name*
GROUP BY h.hacker_id, h.name
HAVING COUNT(h.hacker_id) > 1
ORDER BY COUNT(s.hacker_id) desc, h.hacker_id asc;
