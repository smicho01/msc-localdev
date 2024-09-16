# AcademiChain Docker Compose

This repository is used to deploy AcademiChain application to selected environment using Docker Compose

## Commands

Run application locally with the development set to env variables.
`docker-compose --env-file .env.dev up -d`

Removing containers along with the volumes (all data stored)
`docker-compose --env-file .env.dev down --volumes`