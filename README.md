# FakeApi

Install JSON Server

npm install -g json-server

Create a db.json file with some data

{
  "posts": [
    { "id": 1, "title": "json-server", "author": "typicode" }
  ],
 
 "comments": [
    { "id": 1, "body": "some comment", "postId": 1 }
  ],
 
 "profile": { "name": "typicode" }
}

Start JSON Server

json-server --watch db.json
Now if you go to http://localhost:3000/posts/1, you'll get

{ "id": 1, "title": "json-server", "author": "typicode" }
Also when doing requests, it's good to know that:

If you make POST, PUT, PATCH or DELETE requests, changes will be automatically and safely saved to db.json using lowdb.
Your request body JSON should be object enclosed, just like the GET output. (for example {"name": "Foobar"})
Id values are not mutable. Any id value in the body of your PUT or PATCH request will be ignored. Only a value set in a POST request will be respected, but only if not already taken.
A POST, PUT or PATCH request should include a Content-Type: application/json header to use the JSON in the request body. Otherwise it will result in a 200 OK but without changes being made to the data.
Routes
