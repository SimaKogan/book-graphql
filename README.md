# book-graphql

Book library GraphQL service: Spring Boot 3, Spring GraphQL,
Spring Data JPA, PostgreSQL.

## Run

PostgreSQL (example with Docker):

    docker run --name book-pg -e POSTGRES_PASSWORD=pass -p 5432:5432 -d postgres:16

Application:

    DB_PASSWORD=pass ./mvnw spring-boot:run

Settings (environment variables): `DB_URL`, `DB_USERNAME`, `DB_PASSWORD`
(required).

Tables are created automatically (`ddl-auto=update`) and start empty:
insert books into `book_library`, `book_credential`, `book_status`
to get non-empty answers.

## Use

- GraphQL endpoint: http://localhost:8080/graphql
- GraphiQL UI: http://localhost:8080/graphiql
- Ready-made queries and mutations: `graphql-requests.txt`
- Schema: `src/main/resources/graphql/schema.graphqls`

## Test

    ./mvnw test

Tests use an in-memory H2 database (profile `test`), no PostgreSQL needed.
