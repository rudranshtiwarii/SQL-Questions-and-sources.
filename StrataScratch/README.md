## Users with Many Searches

Count the number of users who made more than 5 searches in August 2021.

SELECT COUNT(search_id) AS Number_of_searches, user_id FROM fb_searches
WHERE MONTH(date) = 8
GROUP BY user_id
HAVING COUNT(search_id) > 5;
