# Raceday_POE

## Overview

The RaceDay Event Management System is a database and REST API planning
project for managing race-day events, users, categories, routes,
enrolments, and race results.

The project is divided into: - Section A: Entity Relationship Diagram
(ERD) - Section B: API Endpoint Plan - Section C: SQL Database Script

# Section A -- Entity Relationship Diagram

The ERD contains six entities: 1. USER 2. EVENTS 3. CATEGORIES 4. ROUTE
5. ENROLMENT 6. RESULTS

The main relationships connect users with events and enrolments, events
with categories and routes, and enrolments with results.

# Section B -- API Endpoint Plan

The REST API is organised around the six entities in the ERD.

## Users

POST /api/auth/register -- register a new user

POST /api/auth/login -- authenticate a user

GET /api/users/{id} -- retrieve a user

PUT /api/users/{id} -- update a user

GET /api/users -- list users

DELETE /api/users/{id} -- delete a user

## Events

GET /api/events -- list events

GET /api/events/{id} -- retrieve an event

POST /api/events -- create an event

PUT /api/events/{id} -- update an event

DELETE /api/events/{id} -- delete an event

## Routes

GET /api/routes -- list available routes

POST /api/routes -- create a route

## Categories

GET /api/events/{id}/categories -- list event categories

POST /api/events/{id}/categories -- add a category

PUT /api/categories/{id} -- update a category

DELETE /api/categories/{id} -- remove a category

## Enrolments

GET /api/events/{id}/enrolments -- list event enrolments

POST /api/events/{id}/enrolments -- enrol a user

GET /api/enrolments/{id} -- retrieve an enrolment

DELETE /api/enrolments/{id} -- remove an enrolment

## Results

GET /api/events/{id}/results -- list results for an event

POST /api/enrolments/{id}/results -- record a result

GET /api/results/{id} -- retrieve a result

PUT /api/results/{id} -- update a result

DELETE /api/results/{id} -- delete a result

# Access Roles

Public users can register, log in and view public event information.

Members can enrol in events and manage their own enrolments.

Organisers can manage events, categories, routes and results.

Administrators can perform user and administrative operations.

Common responses include 200 OK, 201 Created, 400 Bad Request, 401
Unauthorized, 404 Not Found and 409 Conflict.

# Section C -- SQL Database

The database is named race_day.

It contains six tables:

## USER

user_id -- Primary Key

name

surname

role

## ROUTE

route_id -- Primary Key

name

distanceKM

## EVENTS

event_id -- Primary Key

event_name

Description

user_id -- Foreign Key

route_id -- Foreign Key

## CATEGORIES

category_id -- Primary Key

name

event_id -- Foreign Key

## ENROLMENT

enrolment_id -- Primary Key

enrolment_date

event_id -- Foreign Key

user_id -- Foreign Key

## RESULTS

results_id -- Primary Key

finishTime

position

enrolment_id -- Foreign Key

# Foreign-Key Relationships

EVENTS.user_id        -> USER.user_id
EVENTS.route_id       -> ROUTE.route_id
CATEGORIES.event_id   -> EVENTS.event_id
ENROLMENT.event_id    -> EVENTS.event_id
ENROLMENT.user_id     -> USER.user_id
RESULTS.enrolment_id  -> ENROLMENT.enrolment_id

# SQL Features

The SQL script demonstrates primary keys, foreign keys, identity
columns, NOT NULL constraints, CHECK constraints, sample INSERT
statements and SELECT statements for checking the data.

# Project Structure

RaceDay/
├── docs/
│   ├── ERD.png
│   ├── Endpoint-Plan.md
│   └── RaceDaySchema.sql
├── README.md
└── .github/
    └── workflows/
        └── ci.yml

# Technologies and Tools

SQL Server

SQL Server Management Studio (SSMS)

REST API

HTTP methods

GitHub

GitHub Actions

# Running the SQL Script

Open SQL Server Management Studio.

Open the RaceDay SQL script.

Execute the database creation statement.

Execute the table creation statements.

Insert the sample records.

Run the SELECT statements to verify the data.

# GitHub and Continuous Integration

GitHub is used to manage the project files and documentation. GitHub
Actions can be used to validate required project files when changes are
pushed to the repository.

# References

Microsoft (2024) CREATE TABLE (Transact-SQL). Microsoft Learn.

Microsoft (2024) Primary and foreign key constraints. Microsoft Learn.

Coronel, C. and Morris, S. (2019) Database Systems: Design,
Implementation, & Management. 13th edn. Boston: Cengage Learning.

# Author

Ndamulelo Godfrey Tshivhula
Student Number: ST10488805
Module: Programming 2B
Group: 3
