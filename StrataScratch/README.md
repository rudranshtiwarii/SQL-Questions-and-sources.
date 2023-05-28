## Users with Many Searches

Count the number of users who made more than 5 searches in August 2021.

SELECT COUNT(search_id) AS Number_of_searches, user_id FROM fb_searches
WHERE MONTH(date) = 8
GROUP BY user_id
HAVING COUNT(search_id) > 5;




## Blocked Users
You are given a table of users who have been blocked from Facebook, together with the date, duration, and the reason for the blocking. The duration is expressed as the number of days after blocking date and if this field is empty, this means that a user is blocked permanently.
For each blocking reason, count how many users were blocked in December 2021. Include both the users who were blocked in December 2021 and those who were blocked before but remained blocked for at least a part of December 2021.

Table: fb_blocked_users
# For each blocking reason, count how many users were blocked in December 2021. 

select block_reason,COUNT(user_id) from fb_blocked_users
WHERE MONTH(block_date) <= 12 AND (block_duration IS NULL OR block_date + INTERVAL block_duration DAY >= '2021-12-01')
GROUP BY block_reason 
;
