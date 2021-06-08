# Technical test

## Introduction

The purpose of this test is to ensure you have some basic knowledge of the
golang's standard http library, and that you are familiar with objects.

You have to build an http server that is protected by authentication
and returns a simple response.

## Deliverable

To deliver the test, fork this project and provide the following items:

- The source code of the golang http server, with simple build instructions.
- All necessary script to create and seed the different databases.
- The software will be compiled with the latest go version.
- The software and its ecosystem will be run and tested on a local computer.

_Note: You can use Docker and docker-compose to provide the databases._
_Note: Use makefile for build, testing, running and starting dependencies._

## Authentication

The authentication is done by basic auth.
The credentials must be checked in postgres.

| field | type |
| --- | --- |
| id | int |
| login | string |
| password | string |
| first_name | string |
| last_name | string |
| email | string |

_Note: We expect the usage of an interface here._

## Response

The server should return the authenticated user or an error.
The potential internal errors must not be returned in the reponse,
but every request must be logged.

Expected response:
```
    {
        "ID": "1",
        "FirstName": "Steve",
        "LastName": "Rogers"
        "Email": "s.rogers@avenge.rs"
    }
```

The HTTP return codes can be `200`, `401` and `500`

## Evaluation

The evaluation criterium are:

1. Validity
    - The software must do what it is supposed to do.

2. Maintainability 
    - The source code should use interfaces.
    - The source code should follow golang naming conventions.
    - The source code must be readable.
    - The source code must be tested.
    - The source code must be commented.
 
3. Exploitability
    - The support team must be able to troubleshoot with the logs.
    - The configuration must be easy.
    - The software must be documented.
    - The software must be easy to deploy.

4. Security
    - The password must be crypted in database.
    - No secret must be present in the repository (password, etc.)

## Help!

- If you are a new gopher, there is a great golang tutorial
[here](https://tour.golang.org/welcome/1).
- If you look for a pretty design, at Mailjet, we tend to follow the
[Ben Johnson's architecture](https://medium.com/@benbjohnson/standard-package-layout-7cdbc8391fc1).
- Should you need help to write your code or beat your compiler, feel free to
ask us directly!
