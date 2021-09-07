# Project 2: Data Modeling with Apache Cassandra
## Project Description
This project is aimed to help a startup called *Sparkify* analyze the data they've been collecting on songs and user activity on their new music streaming app. 
The challenge is that the analytics team does not have an easy way to query their data, which originally resides in CSV format.

The goal is to create an Apache Cassandra database which can fulfil queries on song play data to answer the questions of what songs users are listening to, as well as a ETL pipeline using Python.

## Apache Cassandra Database Schema
The dataset in a CSV format is located in the `event_data`. The directory of CSV files partitioned by date.<br>
The event data file `event_datafile_new.csv` is used to insert data into Apache Cassandra database and contains the following columns:
- artist
- firstName (of user)
- gender (of user)
- itemInSession (item number in session)
- lastName (of user)
- length (of the song)
- level (paid or free song)
- location (of the user)
- sessionId
- song (title)
- userId

 The data model answers the following queries:
1. Give me the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession = 4
2. Give me only the following: name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182
3. Give me every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'

The NoSQL database includes three tables:
1. `artist_song_data` includes artist, song title, and song length information for a given `sessionId` and `itemInSession` 
2. `artist_song_user_data` includes artist, song title, user first and user last name for given `userId` and `sessionId` ordering the data by `itemInSession`
2. `user_song_data` includes user first and last name for a given song 

All example queries are returned as pandas dataframes to ease further work with extracted data

## How to run the script

The Jupyter Notebook file **Project_1B_Apache_Cassandra.ipynb** with ETL pipeline can be run from terminal with these commands:

        jupyter nbconvert --execute --clear-output test.ipynb

As next, you can open .ipynb file in IDE like *PyCharm* or in *Jupyter Notebook* to see the output of cells.<br>
Alternatively, the file can be run directly in IDE like *PyCharm* or in *Jupyter Notebook* where one should execute cells code.
