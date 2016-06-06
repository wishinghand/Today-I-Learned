This snippet lets you count the number of times a selection is in a table.

`SELECT account_number, COUNT( * ) 
FROM  `stockcar_picks` 
GROUP BY account_number
HAVING COUNT( * ) >=3
LIMIT 0 , 30`