## Project 1: Data Modeling with Postgres

#### Introduction
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

#### Description
This project is to define fact and dimension tables for a star schema, and write an ETL pipeline that transfers data from files in two local directories into these tables in Postgres using Python and SQL.

#### Database Schema
Fact table: songplays <br>
Dimensions tables: songs, artists, users, and start_time
* Fields with underline are primary keys.
![schema](./image/StarSchema.png)

#### ETL Pipeline
* Create a database called sparkifydb
* Create tables as needed based on the star schema
* Load and transform the data from json files (log_data and song_data) <br>
```drop_duplicate(keep = 'first')``` is used when reading the json file
* Insert the data to the corresponding tables
* Test the database

#### How to Run
* Run `` create_tables.py`` to create tables in the sparkifydb database
* Run `` etl.py`` to execute the ETL process

#### Example Query
<I> How many songs does an artist have on Sparkify?
</I>
``` SQL
SELECT artist_id, count(song_id) FROM songs group by artist_id LIMIT 5;
```
