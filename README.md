# demo-online-store
###Build and run
* [Install JDK 11](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)
* [Install Maven](https://maven.apache.org/install.html)
* [Install Docker](https://docs.docker.com/compose/install/)

in root folder run: 

1) Run the environment with PostgreSQL
`docker-compose up -d`

2) Build project
`mvn package spring-boot:repackage`

3) Run executable jar
`java -jar target/demo-online-store.jar` 


##Or 
1) import project to ide, run db `docker-compose up -d` and start DemoOnlineStoreApplication main
##End points
Get all products

GET http://localhost:8080/products/all

Response
```json
[
    {
        "id": 1,
        "brand": "KULTE",
        "model": "26 ММ",
        "price": "12700.00",
        "amount": 30,
        "description": "watches"
    },
    {
        "id": 2,
        "brand": "TECHNE",
        "model": "30 ММ",
        "price": "15700.00",
        "amount": 20,
        "description": "watches"
    },
    {
        "id": 3,
        "brand": "apple",
        "model": "xr",
        "price": "30000.00",
        "amount": 10,
        "description": "mobile phone"
    },
    {
        "id": 4,
        "brand": "samsung",
        "model": "xr",
        "price": "30000.00",
        "amount": 30,
        "description": "mobile phone"
    }
]
```

Get product by id

http://localhost:8080/products/1 // Id 1 for example

Response
```json
{
    "id": 1,
    "brand": "KULTE",
    "model": "26 ММ",
    "price": "12700.00",
    "amount": 30,
    "description": "watches"
}
```

Get products by Brand

http://localhost:8080/products?brand=apple
```json
[
    {
        "id": 3,
        "brand": "apple",
        "model": "xr",
        "price": "30000.00",
        "amount": 10,
        "description": "mobile phone"
    }
]
```
