# docker-compose for the gloabl service : extractor + API

The composition allows you to start a global service API to manage the forecast data from grib files (ww3, gfs for example)

## extractor

Extract data from grib files and store in a MongoDB

You can compose locally with a relative path in **docker-compose.yml**

    #image: happysession/extractor
    build: ../extractor

## API

Set a server REST for data store in MongoDB on http://127.0.0.1:3000

Use NodeJS and NestJS framework.

Publish API with a Swagger on http://127.0.0.1:3000/api

You can compose locally with a relative path in **docker-compose.yml**

    #image: happysession/api
    build: ../api

## Mongo

Mongo container is mounted on a volume './data'.

You can share this volume with 'extractor' and 'api' for convenience

## TODO

- secure MongoDB access
- set indexes for MongoDB performance optimization
