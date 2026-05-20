# World Cup Database

A PostgreSQL database project built as part of the freeCodeCamp Relational Database certification.

## Project Description

This project involves building a database of World Cup games from 2014 and 2018, inserting data from a CSV file, and querying the database to find various statistics.

## Files

- `worldcup.sql` — PostgreSQL database dump containing the full schema and data
- `insert_data.sh` — Bash script that reads `games.csv` and inserts data into the database
- `queries.sh` — Bash script containing queries to retrieve statistics from the database

## Database Structure

### Tables

**teams**
- `team_id` — SERIAL PRIMARY KEY
- `name` — VARCHAR, NOT NULL, UNIQUE

**games**
- `game_id` — SERIAL PRIMARY KEY
- `year` — INT, NOT NULL
- `round` — VARCHAR, NOT NULL
- `winner_id` — INT, FOREIGN KEY referencing teams
- `opponent_id` — INT, FOREIGN KEY referencing teams
- `winner_goals` — INT, NOT NULL
- `opponent_goals` — INT, NOT NULL

## How to Use

### Restore the database
```bash
psql --username=postgres < worldcup.sql
```

### Run the insert script
```bash
./insert_data.sh
```

### Run the queries
```bash
./queries.sh
```

## Technologies Used

- PostgreSQL
- Bash scripting
- Git
