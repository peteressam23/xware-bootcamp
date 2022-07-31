# Exercise mongoDB
- Structure of 'restaurants' collection:
- {
  "address": {
     "building": "1007",
     "coord": [ -73.856077, 40.848447 ],
     "street": "Morris Park Ave",
     "zipcode": "10462"
  - },
  - "borough": "Bronx",
  - "cuisine": "Bakery",
  - "grades": [
     { "date": { "$date": 1393804800000 }, "grade": "A", "score": 2 },
     { "date": { "$date": 1378857600000 }, "grade": "A", "score": 6 },
     { "date": { "$date": 1358985600000 }, "grade": "A", "score": 10 },
     { "date": { "$date": 1322006400000 }, "grade": "A", "score": 9 },
     { "date": { "$date": 1299715200000 }, "grade": "B", "score": 14 }
  - ],
  - "name": "Morris Park Bake Shop",
  - "restaurant_id": "30075445"
- } 

- Write a MongoDB query to display all the documents in the collection restaurants.
- Write a MongoDB query to display the fields restaurant_id, name, borough and cuisine for all the documents in the collection restaurant.
- Write a MongoDB query to display the fields restaurant_id, name, borough and cuisine, but exclude the field _id for all the documents in the collection restaurant.
- Write a MongoDB query to display the fields restaurant_id, name, borough and zip code, but exclude the field _id for all the documents in the collection restaurant.
- Write a MongoDB query to display all the restaurant which is in the borough Bronx.
- Write a MongoDB query to display the first 5 restaurant which is in the borough Bronx.
- Write a MongoDB query to display the next 5 restaurants after skipping first 5 which are in the borough Bronx.
- Write a MongoDB query to find the restaurants who achieved a score more than 90.
- Write a MongoDB query to find the restaurants that achieved a score, more than 80 but less than 100.
- Write a MongoDB query to find the restaurants which locate in latitude value less than -95.754168.

________________________________________________________________________________________________________________________________

## Solution
```
mongosh

use rest

db.resturant.insert({address : {buliding : '1007' , coord : [-73.856077 , 40.848447] , street :'Morris Park Ave' ,  zipcode : '10462'} ,  borough : 'Bronx' , cuisine : 'Bakery' , grades : [ {date : { $date : 1393804800000 } , grade : 'A' , score : 2 } ,  { date : { $date : 1378857600000 } , grade:'A' , score : 6} , {date : { $date:1358985600000 } , grade :'A' , score : 10} , {date : { $date : 1322006400000} , grade : 'A' , score : 9} , {date : {$date:1299715200000} , grade :'B' , score : 14}] , name :'Moris Park Bake Shop' , resturant_id : '30075445'});

db.resturant.find();

db.resturant.find({},{restaurant_id:'30075445',name:'Moris Park Bake Shop' ,borough:'Bronx',cuisine:'Bakery'});

db.resturant.find({},{"resturant_id" : 1,"name":1,"borough":1,"cuisine" :1,"_id":0});

db.resturant.find({},{"restaurant_id" : 1,"name":1,"borough":1,"address.zipcode" :1,"_id":0});

db.resturant.find({"borough": "Bronx"});

db.resturant.find({"borough": "Bronx"}).limit(5);

db.resturant.find({"borough": "Bronx"}).skip(5).limit(5);

db.resturant.find({grades : { $elemMatch:{"score":{$gt : 90}}}});

db.resturant.find({grades : { $elemMatch:{"score":{$gt : 80 , $lt :100}}}});

db.resturant.find({"address.coord" : {$lt : -95.754168}});

________________________________________________________________________________________________________________________________



