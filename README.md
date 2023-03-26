# Project: Data Modeling with Postgres

## Introduction

> The Song Dataset is a freely-available collection of audio features and metadata for a million contemporary popular music tracks.
The purposes of the data set are encouraging research on algorithms and providing a reference dataset for evaluating research 
Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. They need to to create a Postgres database with tables designed to optimize queries on song play analysis.

## Running The Python Scripts
> Python scripts can be run terminal that is started from the Launcher or from File>New>Terminal. For example in order to run **create_tables.py** we can use `python3 create_tables.py` codes in the terminal page.

## Explanation of the Files 
> Files in the repository:
    1. **test.ipynb** includes the codes of displaying the first few rows of each table and Sanity Test
    2. **create_tables.py** includes the codes of creating database, tables and dropping tables (it should run this file to reset the tables before each time run the ETL scripts)
    3. **etl.ipynb** includes the codes of reading and processing a single file from song_data and log_data and loads the data into the tables
    4. **etl.py** includes the codes of reading and processing files from song_data and log_data and loads them into the tables. This file produced by using ETL notebook.
    5. **sql_queries.py** includes all the sql queries, and is imported into the create_tables, etl.ipynb, etl.py

## Database schema design and ETL pipeline
> Star schema and batch etl pipline was used in this project. 
    - **A star schema** is a database organizational structure optimized for use in a data warehouse or business intelligence that uses a single large fact table to store transactional or measured data, and one or more smaller dimensional tables that store attributes about the data. 
    - songplay_table is our fact table and it keeps user_id from user_table, artist_id from artist_table, song_id from song_table and start_time from time_table. 
    - **An ETL pipeline** is a specific form of a data pipeline that assists in moving data. It uses a set of processes (extract, transform, and load) to transfer data from a source, transform raw data and process it into an accessible format, and load it into a destination.
    -  Batch pipeline is where a large amount of data is moved at regular intervals. It could be scheduled daily, weekly, or even monthly. No need to move as soon as it's generated like Streaming pipeline.

