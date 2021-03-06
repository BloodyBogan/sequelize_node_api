# Restaurants & Reviews API

> RESTful API for restaurant aggregation and their reviews

Built using Node.js/Express/Sequelize

## Usage

Fill in your config.env file based on the config.env.example file

```
# Install dependencies
npm install

# Run in development
npm run dev

# Run in production
npm start
```

## Docker MySQL Quick Start

```
# Pull the latest MySQL image
docker pull mysql:latest

# Start MySQL instance
docker run --name mysql-dev -e MYSQL_ROOT_PASSWORD=root -d mysql:latest

# Starting the container next time
docker container start mysql-dev

# Get the container ID
docker ps

# Get your MySQL HOST & MySQL PORT
docker inspect YOUR_CONTAINER_ID

# Connect to the bash into the running MySQL container
docker exec -t -i mysql-dev /bin/bash

# Run MySQL client from bash MySQL container
mysql -uroot -proot

# Create database
CREATE DATABASE restaurant_api;
```

## API Endpoints with Roles

### Restaurant Routes

`GET /api/v1/restaurants/` GUEST  
`GET /api/v1/restaurants/:id` GUEST  
`POST /api/v1/restaurants/` ADMIN  
`PATCH /api/v1/restaurants/:id` ADMIN  
`DELETE /api/v1/restaurants/:id` ADMIN

### Review Routes

`GET /api/v1/reviews/` GUEST  
`GET /api/v1/reviews/restaurant/:id` GUEST  
`GET /api/v1/reviews/:id` GUEST  
`POST /api/v1/reviews/` USER  
`PATCH /api/v1/reviews/:id` ADMIN  
`DELETE /api/v1/reviews/:id` ADMIN

## Things To Consider

CSRF Protection
Custom CORS setup  
Tweaking the already-set rate limiting

## Sample Requests

You can find sample requests in the api.http file. Using this file requires the REST Client extension for VS Code

## App Info

### Author

Michal Kaštan

### Version

1.0.0

### License

This project is licensed under the MIT License
