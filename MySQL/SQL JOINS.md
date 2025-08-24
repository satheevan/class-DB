-- INNER JOINS
-- songs in a given playlist -given username and playlist name

```sql
HEADING Its INNER JOIN
-user_name,playlist_name,song_title,artist_name,duration_s -> instead of start 
SELECT *
FROM playLists P
JOIN users u ON u.id = p.user_id
JOIN playlist_song ps ON ps.playlist.id = p.id
JOIN songs s ON s.id  = ps.song_id
JOIN artist a On a.id = s.artist_id;

HEADING Its LEFT JOIN -> FRIST TABLE IS LEFT TABLE

SELECT * FROM user u 
LEFT JOIN playlist p ON p.user_id = u.id
WHERE P.id IS NULL
ORDER BY U.id;

HEADING Its RIGHT JOIN -> FRIST TABLE IS Right TABLE

SELECT * FROM playlist p  
RIGHT JOIN user u ON p.user_id = u.id
WHERE P.id IS NULL
ORDER BY u.id;

HEADING Its FULL OUTER JOIN -> UNION IN MATHAMATICAL TERM



```