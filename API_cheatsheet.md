# APIs

## Contents

- [Introduction](#introduction)
    * [Data API](#data-api)
    * [Configuring an API](#configuring-an-api)

## Introduction 

API stands for,

- **A**pplication

- **P**rogramming

- **I**nterface

This is not a user interface! An API requires you to program on the interface to interact with the application underneath, no fancy buttons. To set up a Java server, you can hand code it or use an API. Third party APIs include Google Maps where it is used by many other companies.

Types of APIs -

- JAVA API
- Android API - can write Java code but translates down to Android
- JAVA OpenGL - graphics
- Jakarta Persistence API (JPA) - Java to SQL  

## Data API

JSON -

* ***Java Script Object Notation***
* data type
* sets up the data much easier to read than xml
* essentially a lot of key and value pairs

RESTful API -

- ***Representational State Transfer***
- data you are sending over is just the representational state
- the source of the data is represented rather than given out since many people are accessing it, otherwise it would only be allowed to one person at a time
- these are stateless, meaning there is no keeping tracking of the request and response cycle as it would get horrendously large
- no functionality, no methods, no full history

## Configuring an API


![api](/images/api.png)

### Setup

![api](/images/api_setup.png)

The ***endpoints*** are the representations received by the client and the ***resource*** is the data in the database.

When a request is made it follows the RESTful convention - 

* Common requests -
    - **GET, POST, PUT, PATCH, DELETE, OPTION, HEAD**
* **GET** - 
    - needs to represent the data 
    - e.g. http://bbc.co.uk/sport/football/234 should represent sports articles specifically football and id 234 ideally
    - when you get back multplie resources, then thats an **INDEX** action
    - e.g. http://bbc.co.uk/sports/football should give a list of football related articles

![get](/images/get_convention.png)
