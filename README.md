# Rust API

This is a simple API written in [Rust](https://www.rust-lang.org/).

## How to run

This code is using a [PostgreSQL](https://www.postgresql.org/) container in [Docker](https://www.docker.com/).

### Docker

To start the PostgreSQL container:

`docker-compose -f docker-compose.no_api.yml up -d`

To end the container:

`docker-compose -f docker-compose.no_api.yml down`

### Cargo

After the container is running, you can execute the application using the following command:

`cargo run`

## Migrations

Generate reversible migration scripts containing both "up" and "down" SQL files:

`sqlx migrate add -r "description"`

To syncronize the database schema with the migration scripts in "`./migrations`", execute:

`sqlx migrate run`

## Endpoints

### Authentication

#### /api/auth/register

Handles the user registration within the API by invoking the `register` route function.

#### /api/auth/login

Handles the user login by invoking the `login` route function.

#### /api/auth/logout

Handles the user logout by invoking the `logout` route function.

### User

#### /api/users/me

This endpoint is accessible exclusively to users with a valid JWT. This function extracts the user's information from the request, filters out sensitive files such as the password, and then returns the result.

#### /api/users

This endpoint is restricted to users having the "admin" role and a valid JWT.
