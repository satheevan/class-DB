Normalizrtion Our Database

GOAL:
    -Move away from a single table desing
    -Create New tables(when to create a new table)
        - artists 
        - songs
        - users
        - paylists
```sql
        CREATE TABLE artist(
            id INT PRIMARY KEY AUTO_INCREMENT,
            name VARCHAR(100) NOT NULL,
        );

        CREATE TABLE songs(
            id INT PRIMARY KEY AUTO_INCREMENT,
            title VARCHAR(100) NOT NULL,
            artist_id 
            INT NOT NULL,
            album VARCHAR(100) NOT NULL,
            duration_s SMALLINT UNSIGNED,
            CONSTRAINT fk_songs_artist FOREIGN KEY (artist_id) REFERENCES artists(id)
        );
         
        CREATE TABLE users(
            id INT PRIMARY KEY AUTO_INCREMENT,
            name VARCHAT(50) NOT NULL,
            UNIQUE KEY uq_user_name
        )
        CREATE TABLE playlists(
            id  NT PRIMARY KEY AUTO_INCREMENT,
            user_id INT NOT NULL,
            name VARCHAR(100) NOT NULL,
            created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
            CONSTRAINT fk_playlists_users FOREIGN KEY (user_id) REFERENCES users(id)
        );
        CREATE TABLE playlist_songs(
            playlist_id INT NOT NULL,
            song_id INT NOT NULL,
            added_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
            PRIMARY KEY(playlist_id,song_id)
            CONSTRAINT fk_ps_playlists_users FOREIGN KEY (playlist_id) REFERENCES playlists(id)
            CONSTRAINT fk_songs_users FOREIGN KEY (song_id) REFERENCES songs(id)
        )
```