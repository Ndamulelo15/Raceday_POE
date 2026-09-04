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
