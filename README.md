# PostgreSQL & Python Tutorial

> **Note:** This is a guided learning project, built step-by-step while following Code Institute's ["PostgreSQL and Python" video series](https://www.youtube.com/watch?v=ysmd9wxbmqw), taught by Tim Nelson. It is not original/independent work — the goal was to learn and practice the underlying concepts (raw SQL, `psycopg2`, SQLAlchemy Core, and the SQLAlchemy ORM) by coding along with the course.

It uses the [Chinook sample database](https://github.com/lerocha/chinook-database) (a fictional digital music store) to practice querying and manipulating a relational database from Python through four progressively more abstract approaches.

## What this project covers

The same set of queries is implemented four times, each using a different layer of abstraction:

| File | Approach | Description |
|---|---|---|
| [`sql-psycopg2.py`](sql-psycopg2.py) | Raw SQL via `psycopg2` | Queries written as plain SQL strings, executed through a database cursor. |
| [`sql-expression.py`](sql-expression.py) | SQLAlchemy Core (Expression Language) | Tables defined as Python objects (`Table`, `Column`); queries built with methods like `.select()` and `.where()` instead of SQL strings. |
| [`sql-orm.py`](sql-orm.py) | SQLAlchemy ORM | Tables defined as Python classes (`Artist`, `Album`, `Track`); rows become instances of those classes. |
| [`sql-crud.py`](sql-crud.py) | SQLAlchemy ORM — CRUD | A new `Programmer` table/model, used to practice Create and Read operations (adding records, committing a session, then querying them back). |

## Tech stack

- **PostgreSQL** — relational database engine
- **Python 3.10**
- **psycopg2-binary** — low-level PostgreSQL driver for Python
- **SQLAlchemy** — SQL toolkit and ORM

## Getting started

### 1. Prerequisites

- PostgreSQL installed and running locally
- Python 3.10+

### 2. Set up the database

```bash
createdb chinook
psql chinook -f Chinook_PostgreSql.sql
```

### 3. Set up the Python environment

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### 4. Run any of the scripts

```bash
python3 sql-psycopg2.py
python3 sql-expression.py
python3 sql-orm.py
python3 sql-crud.py
```

## Project structure

```
.
├── Chinook_PostgreSql.sql   # sample database schema + data
├── requirements.txt          # Python dependencies
├── sql-psycopg2.py           # raw SQL queries
├── sql-expression.py         # SQLAlchemy Core queries
├── sql-orm.py                # SQLAlchemy ORM queries (Chinook tables)
└── sql-crud.py                # SQLAlchemy ORM CRUD practice (Programmer table)
```

## Acknowledgements

- Thanks to Tim Nelson for walking through this [tutorial series](https://www.youtube.com/watch?v=ysmd9wxbmqw) as part of Code Institute's PostgreSQL and Python course.
- Thanks to Luis Rocha for creating and maintaining the [Chinook sample database](https://github.com/lerocha/chinook-database), used throughout this project.
