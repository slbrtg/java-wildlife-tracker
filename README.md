## Wildlife Tracker

An app for the forest service to track animals for an environmental impact study.

### Description

The Forest Service is considering a proposal from a timber company to clearcut a nearby forest of Douglas Fir. Before this proposal may be approved, they must complete an environmental impact study. This application was developed to allow Rangers to track wildlife sightings in the area.

##Changes Made

* The sightings database was altered to fix an issue where an endangered animal with the same id as a regular animal would both be treated as ther same animals.

* Added Constants to define the options available for setting and updating an animal's information

* Complete CRUD functionality for sights, animals, and endangered animals.

* Added an abstract class for the Animal and EndangeredAnimal to extend from.

* Added a timestamp to the sightings table for when the animal was last seen

### Setup

To create the necessary databases, launch postgres, then psql, and run the following commands:

* `CREATE DATABASE wildlife_tracker;`
* `\c wildlife_tracker;`
* `CREATE TABLE animals (id serial PRIMARY KEY, name varchar);`
* `CREATE TABLE endangered_animals (id serial PRIMARY KEY, name varchar, health varchar, age varchar);`
* `CREATE TABLE sightings (id serial PRIMARY KEY, animal_id int, location varchar, ranger_name varchar, endangered_animal_id int);`
* `ALTER TABLE sightings ADD endangered_animal_id int, time timestamp;`
* `CREATE DATABASE wildlife_tracker_test WITH TEMPLATE wildlife_tracker;`

### License

Copyright (c) 2017 **_MIT License_**
