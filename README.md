# Delete-Duplicate-Emails


Problem Link: https://leetcode.com/problems/delete-duplicate-emails/description/?envType=study-plan-v2&envId=top-sql-50

## Solution
- with join
```sql
DELETE P2
FROM Person p1
INNER JOIN Person p2 ON P1.email = p2.email 
AND p1.id < p2.id

```
- with subQuery
 ```sql 
 DELETE FROM person
WHERE id NOT IN (
    SELECT MIN(id)
    FROM person
    GROUP BY email
)
