# AspnetMicroservices
AspnetMicroservices

Docker:

ls

docker ps

docker ps -aq

docker pull mongo

docker images

docker rmi $(docker images -q)

docker run -d -p 27017:27017 --name shopping-mongo mongo

docker logs -f shopping-mongo

docker stop xxxx

docker rm xxxx

docker stop $(docker ps -aq)

docker system prune


Mongo:

docker exec -it shopping-mongo /bin/bash

ls

mongosh

show dbs

use CatalogDb

db.createCollection('Products')

db.Products.insertMany([{"Name": "Laptop", "Category": "Computers", "Summary": "Summary", "Description": "Description", "ImageFile": "ImageFile", "Price": 54.93}])

db.Products.find({}).pretty()

db.Products.remove({})

show collections


MongoClient:

docker run -d -p 3000:3000 mongoclient/mongoclient

http://localhost:3000/


Catalog.API:

GET api/v1/Catalog

GET api/v1/Catalog/{id}

GET api/v1/Catalog/GetProductByCategory/{category}

POST api/v1/Catalog

PUT api/v1/Catalog

DELETE api/v1/Catalog/{id}


Packages:

MongoDB.Driver

Swashbuckle.AspNetCore

Microsoft.Extensions.Caching.StackExchangeRedis

Npgsql

Dapper


Docker compose:

docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml up -d

docker-compose -f .\docker-compose.yml -f .\docker-compose.override.yml down


Redis:

docker pull redis

docker run -d -p 6379:6379 --name aspnetrun-redis redis

docker exec -it aspnetrun-redis /bin/bash

redis-cli

ping

set key value

get key


Basket API:

GET api/v1/Basket

POST api/v1/Basket

DELETE api/v1/Basket/{userName}

POST api/v1/Checkout


DiscountDB:
CREATE TABLE Coupon(
	ID SERIAL PRIMARY KEY NOT NULL,
	ProductName VARCHAR(24) NOT NULL,
	Description TEXT,
	Amount		INT
);