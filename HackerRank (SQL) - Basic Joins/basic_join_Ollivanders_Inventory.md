*Challenge*: https://www.hackerrank.com/challenges/harry-potter-and-wands/problem

*Problem*: In this challenge, we want to return a wand's id, code, coins needed, and power by first finding the minimum cost of a wand of a certain power and age and sorting it by strongest power and then by oldest age.

*Solution*:

SELECT a.id, b.AGE, a.COINS_NEEDED, a.POWER

FROM WANDS a JOIN WANDS_PROPERTY b ON a.CODE = b.CODE

WHERE b.IS_EVIL = 0 AND

a.COINS_NEEDED = (SELECT MIN(WANDS.COINS_NEEDED) FROM WANDS INNER JOIN WANDS_PROPERTY ON WANDS.CODE = WANDS_PROPERTY.CODE

WHERE WANDS.power = a.power and WANDS_PROPERTY.age = b.age) ORDER BY a.POWER desc, b.age desc;
