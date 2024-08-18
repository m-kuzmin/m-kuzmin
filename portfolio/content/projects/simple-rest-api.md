---
title: Simple REST API
date: 2023-07-26
github: m-kuzmin/simple-rest-api
description: "A practice backend service that interacts with an SQL database in Go."
skills:
  - golang
  - postgres
  - docker
  - github-actions
---

## Overview

A simple project, yet powerful learning experience. I learned how to setup a dockerized PostgreSQL database, connect it
to the Go application using docker-compose, make queries securely (SQL injections) using sqlc and create API endpoints
using Gin.

Despite this being an internship, I had to chose the tech stack after doing research myself and I am very happy with the
choices I made back then.

The application itself is not very interesting, it just has some endpoints to create users, search them etc, the details
are in the repo readme, the main value for me was the use of all these tools.

## Tech stack

- **Golang**
  - **Gin** for the REST API
  - **sqlc** for executing SQL queries safely
  - **go-migrate** to automatically migrate the database on service startup
- **PostgreSQL** as the database
- **Docker** to connect **PostgreSQL** and the Go backend server
- **GitHub Actions** for code quality control and SQL query checks.

## Valuable experience

I learned how to use the tools and libraries in the tech stack, did some research and compared them to alternatives. Set
up CI to run checks on the code. Overall I think I learned more in this project, than the rest of my previous Go 
projects.
