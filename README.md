## Introduction
A startup called Sparkify wanted to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team was particularly interested in understanding what songs users are listening to. They didn't have an easy way to query their data, which resided in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

They wanted a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis, and so they brought me on the project. My role was to create a database schema and ETL pipeline for this analysis.

## Database schema
Database Name: sparkifydb
Schema structure: Star schema (1 fact table | 4 dimension tables)

### Fact Table
Table Name: songplays
Purpose: records in log data associated with song plays
Columns: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent

### Dimension Tables
Table Name: users
Purpose: users in the app
Columns: user_id, first_name, last_name, gender, level

Table Name: songs
Purpose: songs in music database
Columns: song_id, title, artist_id, year, duration

Table Name: artists
Purpose: artists in music database
Columns: artist_id, name, location, latitude, longitude

Table Name: time
Purpose: timestamps of records in songplays broken down into specific units
Columns: start_time, hour, day, week, month, year, weekday

## Instructions

** NOTE: To execute locally you must first create your own postgres database and modify all database mentions in both python scripts. And generate / download your own data. The Data and event simulator is available via the following links: (be sure to modify the filepaths in both scripts to match your own directories)
> Song Dataset - http://millionsongdataset.com/
> Log Dataset- https://github.com/Interana/eventsim

* To populate the tables in the database, execute create_tables.py. This
creates "shell schema".

* To run the etl process execute the etl.py file to populate the tables with data.

* Query the database as you normally would.
