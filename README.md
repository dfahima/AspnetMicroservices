# AspnetMicroservices
AspnetMicroservices

Docker:
docker ps

docker pull mongo

docker run -d -p 27017:27017 --name shopping-mongo mongo

docker logs -f shopping-mongo


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


Catalog.API

GET api/v1/Catalog

GET api/v1/Catalog/{id}

GET api/v1/Catalog/GetProductByCategory/{category}

POST api/v1/Catalog

PUT api/v1/Catalog

DELETE api/v1/Catalog/{id}


Packages:
MongoDB.Driver

Swashbuckle.AspNetCore


