Challenge: https://www.hackerrank.com/challenges/contest-leaderboard/problem

SELECT h.hacker_id, h.name, SUM(max_score)
FROM HACKERS h JOIN


(SELECT h.hacker_id, max(s.score) FROM s WHERE
 GROUP BY h.hacker_id, s.challenge_id) as max_score


JOIN SUBMISSIONS s

ON h.hacker_id
