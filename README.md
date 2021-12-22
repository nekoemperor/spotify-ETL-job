# Spotify API ETL Job
Run Spotify API ETL Job in 15 minutes

## Table of contents
* [About](#about)
* [The Demo](#the-demo)
* [Installation](#installation)

## About
This repo covers the entire ETL process based on Spotify API data. 

We are going to build a simple data pipeline (or in other words, a data feed) that downloads Spotify data
on what songs we've listened to in the last 24 hours, and saves that data in a SQLite database.

We will schedule this pipeline to run daily. After a few months we will end up with our own, private Spotify played tracks history dataset!


## The Demo 
Check out the demo: (still run locally, later to be run in docker)
<p align="center"><img src="https://github.com/nekoemperor/salaryprediction-ml-app/blob/master/salaryprediction/images/salaryprediction.gifsadasd" width="768"  />

## Installation
* Clone this repo: [Github repo to clone](https://github.com/karolina-sowinska/free-data-engineering-course-for-beginners)
* Install & Setup Airflow: [Airflow Quickstart](https://airflow.apache.org/docs/apache-airflow/stable/start/local.html)
  - change the content of ```airflow.cfg``` in ```~/airflow```, e.g., from ```dags_folder = /home/<USER>/airflow/dags``` to ```dags_folder = /home/<USER>/spotify-ETL-job/dags``` 
* Add your Spotify Username: 
  - Open your spotify app, click your profile or username, then account. From there copy the 10-digit username, and
  - Paste it in [spotify_etl.py](https://github.com/nekoemperor/spotify-ETL-job/blob/master/dags/spotify_etl.py) line 44:
* Add your Spotify API token: 
  - Generate your Spotify API access token here: https://developer.spotify.com/console/get-recently-played/
  - You can change the song limit (default is 10)
  - Copy the OAuth Token, and paste it in [spotify_etl.py](https://github.com/nekoemperor/spotify-ETL-job/blob/master/dags/spotify_etl.py) line 45
* Open 2 WSL terminals,
  - On terminal 1, run ```airflow webserver --port 8080```
  - On terminal 2, run ```airflow scheduler```
