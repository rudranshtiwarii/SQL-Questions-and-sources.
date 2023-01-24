## 1) Find the review count for one-star businesses from yelp.

select SUM(review_count)
from yelp_business
where stars = '1';
