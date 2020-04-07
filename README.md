# [PacktPub, Florian Goto] RESTful Web API Design with Node.js 12 [ENG, February 28, 2020]


**Course info:**  
https://www.packtpub.com/web-development/restful-web-api-design-with-node-js-12-video


**Original src:**  
https://github.com/PacktPublishing/RESTful-Web-API-Design-with-Node.js-12-contact-api



<!--

<br/>

### [Development](./DEVELOPMENT.md)

<br/>

    $ git reset --hard 8bea5a40298f48539c6f2b779d22d83037c98060

<br/>

    $ node index.js

<br/>

    $ curl \
    --request GET http://localhost:3000/v1/ \
    --header "Content-Type: application/json" \
    --user "admin:supersecret" \
    | python -m json.tool

<br/>

```
{
    "baseUrl": "/v1",
    "headers": {
        "accept": "*/*",
        "authorization": "Basic YWRtaW46c3VwZXJzZWNyZXQ=",
        "content-type": "application/json",
        "host": "localhost:3000",
        "user-agent": "curl/7.58.0"
    },
    "host": "localhost",
    "ip": "::ffff:127.0.0.1",
    "message": "Handling GET request",
    "method": "GET",
    "path": "/"
}
```

-->

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

### 3.1 MongoDB - A Document Store Database

<br/>

### 3.2 Using Mongo Atlas Cloud Services

<br/>

### 3.3 Database Modeling with Mongoose

<br/>

### 3.4 Testing a Mongoose Model with Mocha



---

**Marley**

<a href="https://jsdev.org">jsdev.org</a>
