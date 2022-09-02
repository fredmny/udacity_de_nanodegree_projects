# Project: Database Modelling with Postgres
First project of the Data Engineering Nanodegree from Udacity. 

This project considers an imaginary startup called Sparkify which wants to analyze the data of its music streaming app to understand what songs their users are listening to. Unfortunately the startup has this data only within `json` files and wants a better way to query it. 

To do so, in this project, a Postgres database is created. This database is called `sparkifydb` and consists of five tables: 
- `songplays` (fact table) - log of song plays
- `users` (dimension table) - users in the app
- `songs` (dimension table) - songs the app as in its database
- `artists` (dimension table) - data about the song artists in the database
- `time` (dimension table) - timestamps of the start time for every record in the songplays table broken down in specific units

These tables are in the star schema, making it easy to aggregate data on the songplays fact table and at the same time easy to join with dimension tables for filtering and specify aggregation parameters.

After the creation of these tables the `json` files ar processed and insertes into this tables:
- **song play logs** - populates the `songplays`, `users` and `time` tables
- **song data** - populates the `songs` and `artists` table

## Files
The project consists of following files:
- `sql_queries.py` - Contains all the SQL queries necessary for the project. This file is not to be run by itself, but is imported in other files. The queries:
  - drop tables
  - create tables
  - insert data into tables
  - select artist and song id for the songplays table
- `create_tables.py` - Contains the python code to create the database and drop + create the tables. This file should be run before running the `etl.ipynb` or `etl.py` files
- `etl.ipynb` - Jupyter notebook to create and test each step of the etl process. Used as basis to create `etl.py`
- `etl.py` - Inserts the data contained in the `json` files into the tables. This file should be run each time new data is available and depends on the database and tables created with `create_tables.py`
- Files within `./data/` - `json` files with song play and songs data

## Dependencies
To run the files following libraries (and its dependencies) are necessary:
- `pandas` - Manage dataframes to preprocess data
- `psycopg2` - Connect to Postgres Database

A running Postgres instance with following initial credentials is also necessary to run these files:
- user: `student`
- password: `student`
- database: `studentdb`

TODO:
- update diagram with correct data types