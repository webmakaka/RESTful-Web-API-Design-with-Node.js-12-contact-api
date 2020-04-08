# [PacktPub, Florian Goto] RESTful Web API Design with Node.js 12 [ENG, February 28, 2020]

<!--
# I DO NOT RECOMMEND TO BUY THIS SHITTY COURSE!!!
-->

**Course info:**  
https://www.packtpub.com/web-development/restful-web-api-design-with-node-js-12-video


**Original src:**  
https://github.com/PacktPublishing/RESTful-Web-API-Design-with-Node.js-12-contact-api

<br/>

**Final project:**

<br/>

![Application](./img/pic-final-1.png?raw=true)

<br/>

![Application](./img/pic-final-2.png?raw=true)

<br/>

**To Run projects by docker-compose, need to update at least:**

    - MONGO_USER=admin
    - MONGO_PASS=87654321Mongodb
    - MONGO_HOST=cluster0-y8588.mongodb.net


<br/>

## 2. Building a Typical Web API

<br/>

### 2.1 Specifying the API

    $ npm run start:dev

<br/>

### 2.2 Implementing Routes

    $ npm run start:dev

    $ curl \
    --request GET http://localhost:3000/contacts/ \
    --header "Content-Type: application/json" \
    --user "admin:supersecret2" \
    | python -m json.tool

<br/>

**response:**

```
[
    [
        "324d28ab-f909-4ddb-ac97-e9226d6c8afb",
        {
            "company": "O'Reilly - McKenzie",
            "firstName": "Freida",
            "groups": [
                "Dev",
                "Node.js"
            ],
            "jobTitle": "Corporate Group Liaison",
            "lastName": "Pacocha",
            "otherContactNumbers": [
                "1-050-404-1047",
                "1-098-650-8906 x66529"
            ],
            "otherEmailAddresses": [
                "Scarlett.Swift@gmail.com",
                "Alden_Heidenreich62@gmail.com"
            ],
            "primaryContactNumber": "(546) 741-8865 x70321",
            "primaryEmailAddress": "Delphine.Carroll20@gmail.com",
            "socialMedia": [
                {
                    "link": "http://wyman.info",
                    "name": "Linkedin"
                },
                {
                    "link": "https://norval.biz",
                    "name": "Twitter"
                }
            ]
        }
    ],

***

```

<br/>

### 2.3 Querying the API Using Mock Data

GET, POST, PUT, DELETE - examples

<br/>

### 2.4 Content Negotiation

    $ curl \
    --request GET http://localhost:3000/contacts/ \
    --header "Content-Type: application/json" \
    --user "admin:supersecret2" \
    | python -m json.tool

<br/>

    $ curl \
    --request GET http://localhost:3000/contacts/ \
    --header "Content-Type: text/html" \
    --user "admin:supersecret2"

<br/>

    $ curl \
    --request GET http://localhost:3000/contacts/ \
    --header "Content-Type: text/plain" \
    --user "admin:supersecret2"    

<br/>

### 2.5 API Versioning

    $ curl \
    --request GET http://localhost:3000/v2/ \
    --header "Content-Type: application/json" \
    --user "admin:supersecret" \
    | python -m json.tool


<br/>

## 3. Using NoSQL Databases

<br/>

### 3.1 MongoDB - A Document Store Database (Recomment to skip this step)

    $ docker run -d -p 27017-27019:27017-27019 --name mongodb mongo

    $ npm run start:dev

<br/>

### 3.2 Using Mongo Atlas Cloud Services

    export MONGO_HOST=db-name.mongodb.net
    export MONGO_USER=admin
    export MONGO_PASS=admin

    $ npm run start:dev

<br/>

### 3.3 Database Modeling with Mongoose

Remove current db

Send POST to http://localhost:3000/contacts/many 

without data to create a new db

<br/>

### 3.4 Testing a Mongoose Model with Mocha

    $ npm run test

<br/>

## 4. RESTful API Design Guidelines

<br/>

### 4.1 Endpoint URLs and HTTP Status Codes Best Practices


<br/>

### 4.2 Extensibility and Versioning


GET --> http://localhost:3000/api/v2/contacts


<br/>

### 4.3 Linking Data


<br/>

## 5. Implementing a Full-Fledged RESTful Service

<br/>

### 5.1 Working with Arbitrary Data - Database Layer

<br/>

### 5.2 Working with Arbitrary Data - Business Layer

POST --> http://localhost:3000/api/v2/contacts/<contact_id>/image

GET  --> http://localhost:3000/api/v2/contacts/<contact_id>/image

DELETE  --> http://localhost:3000/api/v2/contacts/<contact_id>/image

<br/>

### 5.3 Linking Your Data

<br/>

### 5.4 Implementing Paging and Filtering

GET  --> http://localhost:3000/api/v2/contacts?offset=10

GET  --> http://localhost:3000/api/v2/contacts?offset=10&limit=10

<br/>

### 5.5 Caching Data

    $ export REDIS_PASSWORD=$(echo "redispass1" | base64)
    $ docker run --name redis-cache -e REDIS_PASSWORD=${REDIS_PASSWORD} -p 6379:6379 redis redis-server --requirepass ${REDIS_PASSWORD}

    $ sudo apt install -y redis-tools

<br/>

    $ export REDIS_PASSWORD=$(echo "redispass1" | base64)
    $ echo ${REDIS_PASSWORD}

    $ redis-cli -h localhost -p 6379

    $ localhost:6379> AUTH cmVkaXNwYXNzMQo=

    localhost:6379> HSET mykey myfield myvalue
    (integer) 1
    localhost:6379> keys *
    1) "mykey"
    localhost:6379> HGET mykey myfield
    "myvalue"
    localhost:6379> 
    localhost:6379> EXPIRE mykey 10

<br/>

### 5.6 Caching Data - Business Logic

    $ export REDIS_HOST=localhost
    $ export REDIS_PORT=6379

    $ npm run star:dev

<br/>

GET  --> http://localhost:3000/api/v2/contacts?offset=1&limit=5

<br/>

## 6 Securing the Application

<br/>

### 6.1 Cross-Origin Resource Sharing (CORS)

    $ export CORS_WHITELIST=https://js.do
    $ npm run star:dev

<br/>

![Application](./img/pic-6-1.png?raw=true)

<br/>

![Application](./img/pic-6-2.png?raw=true)

<br/>

### 6.2 Rate Limiting

    $ export RATE_LIMIT_MAX_REQUESTS=2

    // 15 minutes
    $ export RATE_LIMIT_WINDOW_MS=$((16*60*1000))

GET  --> http://localhost:3000/api/v2/contacts?offset=1&limit=5


<br/>

### 6.3 Authentication - Database Logic

<br/>

### 6.4 Authentication Business Logic: Using Tokens

**NOT WORKS FOR ME!!!**

    $ npm run star:dev

<br/>

    $ curl \
    -d '{"firstName":"Joe", "lastName":"Black", "credential": {"password":"123456789"}, "primaryEmailAddress" : "joe.black@example.com"}' \
    -H "Content-Type: application/json" \
    -X POST localhost:3000/auth/sign-up \
    --user "admin:supersecret2" \
    | python -m json.tool


<br/>

**response**

<br/>

    {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7Im90aGVyQ29udGFjdE51bWJlcnMiOltdLCJvdGhlckVtYWlsQWRkcmVzc2VzIjpbXSwiZ3JvdXBzIjpbXSwiY29udGFjdHMiOltdLCJfaWQiOiI1ZThlMGZiMGRjY2Y0MzA5OTg0Yjk3OTAiLCJmaXJzdE5hbWUiOiJKb2UiLCJsYXN0TmFtZSI6IkJsYWNrIiwicHJpbWFyeUVtYWlsQWRkcmVzcyI6ImpvZS5ibGFja0BleGFtcGxlLmNvbSIsInNvY2lhbE1lZGlhIjpbXX0sImlhdCI6MTU4NjM2ODQzMiwiaXNzIjoiY29udGFjdHNkYi5jb20iLCJzdWIiOiI1ZThlMGZiMGRjY2Y0MzA5OTg0Yjk3OTAifQ.GhQnsuwyN1RqYvfKU_i55Z_lXS1DUpmeZ88ORY2QTWw"

    }

<br/>

    $ curl \
    -d '{"password":"123456789", "email": "joe.black@example.com"}' \
    -H "Content-Type: application/json" \
    -X POST localhost:3000/auth/sign-in \
    --user "admin:supersecret2" \
    | python -m json.tool

<br/>

**response:**

    {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7Im90aGVyQ29udGFjdE51bWJlcnMiOltdLCJvdGhlckVtYWlsQWRkcmVzc2VzIjpbXSwiZ3JvdXBzIjpbXSwiY29udGFjdHMiOltdLCJfaWQiOiI1ZThlMGZiMGRjY2Y0MzA5OTg0Yjk3OTAiLCJmaXJzdE5hbWUiOiJKb2UiLCJsYXN0TmFtZSI6IkJsYWNrIiwicHJpbWFyeUVtYWlsQWRkcmVzcyI6ImpvZS5ibGFja0BleGFtcGxlLmNvbSIsInNvY2lhbE1lZGlhIjpbXX0sImlhdCI6MTU4NjM2ODQ0NSwiaXNzIjoiY29udGFjdHNkYi5jb20iLCJzdWIiOiI1ZThlMGZiMGRjY2Y0MzA5OTg0Yjk3OTAifQ.VNXYHht4GIGdqUxiELcIlAME9e9iVPwB4FfzA1i1624"
    }



<br/>

### 6.5 Authorization - Guarding Routes with Middleware

    $ export JWT_TOKEN_SECRET=$(openssl rand -base64 1400)
    $ export JWT_TOKEN_ISSUER="contactsdb.com"

Bearer auth with token

<br/>

### 6.6 Authorization - Business Logic

Send post request with token authentication

<br/>

## 7. Preparing a RESTful API for Production

<br/>

### 7.1 Documenting RESTful APIs with OpenAPI (Swagger)

http://localhost:3000/api/docs/v2/

<br/>

### 7.2 Using PM2 for Production Process Management

<br/>

### 7.3 Dockerizing the App

<br/>

### 7.4 Source Control with AWS CodeCommit

<br/>

### 7.5 Creating an AWS IAM Role

<br/>

### 7.6 Setting an AWS EC2 Instance

<br/>

### 7.7 Deploying the Application


<br/>

## 8. Consuming an API

<br/>

### 8.2 Setting Up the Web Application Server

    $ cd client
    $ npm run start:dev

localhost:5000

<br/>

### 8.3 Handling Errors on the Frontend

<br/>

### 8.4 Signing Up and Signing In

<br/>

### 8.5 Displaying Logged User Contacts

<br/>

### 8.6 Creating Contacts

<br/>

### 8.7 Deploying the Web App Microservice

<br/>

### 8.8 Course Summary

---

**Marley**

<a href="https://jsdev.org">jsdev.org</a>
