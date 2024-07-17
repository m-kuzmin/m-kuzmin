---
title: Spy Cat Agency Management System
github: m-kuzmin/sca-management-system
date: 2024-07-03
description: Dockerized backend REST API in Golang to manage the Spy Cat Agency
skills:
  - golang
  - postgres
  - docker

draft: true
---

# Overview

The SCA (test task force) needed a backend server for managing their cat agents. Cats would go on missions and spy on 
1-3 targets. They would update their notes and eventually mark the target as complete.

- Agents can be assigned to a mission. After a mission or a target is complete the notes can not be changed anymore.
- The agent's breed had to be validated using <https://thecatapi.com>.

There were some additional constraints set by the SCA, but those aren't important enough to be listed here.

# Tech stack

- **Golang** for the backend server
- **PostgreSQL** database to store cat, mission and target information
- **sqlc** allowed to safely and ergonomically use raw SQL for queries. Although the query file was getting out of hand 
  a bit...
- **go-migrate** as the database migration tool (Go server would migrate the DB on startup)
- **Docker** (and docker-compose) for obvious reasons. Easy DB setup, no build tools required on the runner machine etc.

# Valuable experience

While implementing the backend service, I practiced using a variety of tools to interface with SQL databases. I did face
some issues, however. For example, just stopping a docker container is not enough to delete the database file. You have
to run `docker-compose down` to completely clear the container state. I didn't know that before! And that caused some
migration issues when I tried to change the schema without resetting the test database.

Overall I brushed up on concepts I had experience with, but hadn't used for some time. While this project is very 
similar to [another one I did](../simple-rest-api), I did make some improvements. Such as replacing the unnecessary checks to ensure 
auto-generated code was not modifed, the generated code is now gitignored and generated at build time in docker. If
anything, this test task will be useful to me as work experience.