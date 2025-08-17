```sql
# How many rows are in the tabele?

SELECT COUNT(*) FROM TABLE_NAME;

# Top 3 longest tracks Overall
SELECT * FROM TABLE_NAME ORDER BY COLUMN_NAME1 DESC, COLUMN_NAME2 LIMIT 5;

# Count of songs per artist
SELECT COLUMN_NAME1, COUNT(*) AS COLUMN_NAME2 FROM TABLE_NAME
GROUP BY COLUMN_NAME1;
#when using the GROUP Clause donot use the where Condition

# ALBUM that appear at least twice
SELECT COLUMN_NAME1, COUNT(*) AS COLUMN_NAME2 FROM TABLE_NAME
GROUP BY COLUMN_NAME1 HAVING COUNT(*) >= 2;

# Songs added in that 7 days
SELECT * FROM TABLE_NAME
WHERE COLUMN_NAME1 >= CURRENT_DATE - INTERVAL 70 DAY;

# Pagination : 3 most recent songs after skipping 2;
# 2nd page where we retrive two results per page

SELECT * FROM TABLE_NAME ORDER BY COLUMN_NAMEM DESC LIMIT 3 OFFSET 2;

```
## observation

Duplication : artist_name, album_name,duration
updating : fixing an artist's name required editing many rows
INSERT: insertion for a song, artist or album is only possit
Deletion,
Storage,