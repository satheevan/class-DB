```sql

--songs that are longer than 200 seconds
SELECT id,title,duration_s FROM songs WHERE duratin_s > 200 ORDER BY duration_s DESC;

--songs that start E
SELECT id, title FROM songs
WHERE tile LIKE '%E';

-- Distinct album names we have on record
SELECT DIS

--see the top 5 recently created playlist
SELECT * FROM playlists ORDER BY created_at DESC LIMIT 5;

--Number of Playlist per user
SELECT user_id COUNT(*) FROM playlists GROUP BY user_id;

-- Pagination page 2,each  page has 5 rows
SELECT id,title FROM songs ORDER BY title LIMIT BY title LIMIT 5 OFFSET 5;

--POSSIBLE DUPLICATE TITLES WITH DIFFERENT CASTING
SELECT LOWER(title) as title_lowerCase ,COUNT(DISTINCT title) AS variant, COUNT(*) AS total_rows FROM songs
GROUP BY LOWER(title);

--sanity checks for odd data - duration_s
SELECT id, title,duration_s FROM songs WHERE duaration_s IS NULL OR duaration_s = 0;

```
