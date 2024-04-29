# Rust API

This is a simple API written in Rust.

## How to run

### Start the container

Launching the [PostgresSQL](https://www.postgresql.org/) container:

`docker-compose -f docker-compose.no_api.yml up -d`

### Disable the container

`docker-compose -f docker-compose.no_api.yml down`

## Migrations

Generate reversible migration scripts containing both "up" and "down" SQL files:

`sqlx migrate add -r "description"`

To syncronize the database schema with the migration scripts in "/migrations", execute:

`sqlx migrate run`
