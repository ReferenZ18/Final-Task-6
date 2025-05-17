# Final Task 6 - MongoDB Practice

In this task, we used and learned the MongoDB software, following the provided step-by-step guide from our Instructor.
 

## Queries

<p align="center">
  1. Get all documents. <br> Code: <code>db.movies.find()</code>
</p>
<p align="center">
  <img src="Images/Q1.PNG" alt="Alt Text" width="600">
</p>

<p align="center">
  2. Get all documents with "Writer" set to "Quentin Tarantino". <br> Code: <code>db.movies.find({writer:"Quentin Tarantino"})</code>
</p>
<p align="center">
  <img src="Images/Q2.PNG" alt="Alt Text" width="600">
</p>

<p align="center">
  3. Get all documents where "actor" includes Brad Pitt. <br> Code: <code>db.movies.find({actors:"Brad Pitt"})</code>
</p>
<p align="center">
  <img src="Images/Q3.PNG" alt="Alt Text" width="600">
</p>

<p align="center">
  4. Get all documents with "Franchise" set to "The Hobbit". <br> Code: <code>db.movies.find({franchise:"The Hobbit"})</code>
</p>
<p align="center">
  <img src="Images/Q4.PNG" alt="Alt Text" width="600">
</p>

<p align="center">
  5. Get all movies released in the 90s. <br> Code: <code>db.movies.find({year:{$gt:"1990", $lt:"2000"}})</code>
</p>
<p align="center">
  <img src="Images/Q5.PNG" alt="Alt Text" width="600">
</p>

<p align="center">
  6. Get all movies released before the year 2000 or after 2010. <br> Code: <code>db.movies.find({$or:[{year:{$gt:"2010"}},{year: {$lt:"2000"}}]})</code>
</p>
<p align="center">
  <img src="Images/Q6.PNG" alt="Alt Text" width="1200">
</p>


## Documents Update

<p align="center">
  1. Add a synopsis to "The Hobbit An Unexpected Journey": "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home and the gold within it - from the dragon Smaug."
</p>
<p align="center">
  Code: <code>db.movies.update({title: "The Hobbit An Unexpected Journey"}, {$set: {synopsis: "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home and the gold within it - from the dragon Smaug."}})</code>
</p>
<p align="center">
  <img src="Images/U1.PNG" alt="Alt Text" width="1400">
</p>

<p align="center">
  After Update:
</p>
<p align="center">
  <img src="Images/U1R.PNG" alt="Alt Text" width="1400">
</p>

<p align="center">
  2. Add a synopsis to "The Hobbit: The Desolation of Smaug": "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
</p>
<p align="center">
  Code: <code>db.movies.update({title: "The Hobbit: The Desolation of Smaug"}, {$set: {synopsis: "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})</code>
</p>
<p align="center">
  <img src="Images/U2.PNG" alt="Alt Text" width="1400">
</p>

<p align="center">
  After Update:
</p>
<p align="center">
  <img src="Images/U2R.PNG" alt="Alt Text" width="1400">
</p>

<p align="center">
  3. Add an actor named "Samuel L. Jackson" to the movie "Pulp Fiction"
</p>
<p align="center">
  Code: <code>db.movies.update({title: "Pulp Fiction"}, {$push: {actors: "Samuel L. Jackson"}})</code>
</p>
<p align="center">
  <img src="Images/U3.PNG" alt="Alt Text" width="600">
</p>

<p align="center">
  After Update:
</p>
<p align="center">
  <img src="Images/U3R.PNG" alt="Alt Text" width="600">
</p>

## Text Search

<p align="center">
  1. Find all movies that have a synopsis that contains the word "Bilbo". <br> Code: <code>db.movies.find({synopsis:{$regex:"Bilbo"}})</code>
</p>
<p align="center">
  <img src="Images/T1.PNG" alt="Text for Query 1" width="1200">
</p>

<p align="center">
  2. Find all movies that have a synopsis that contains the word "Gandalf". <br> Code: <code>db.movies.find({synopsis:{$regex:"Gandalf"}})</code>
</p>
<p align="center">
  <img src="Images/T2.PNG" alt="Text for Query 2" width="1200">
</p>

<p align="center">
  3. Find all movies that have a synopsis that contains the word "Bilbo" and not the word "Gandalf". <br> Code: <code>db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})</code>
</p>
<p align="center">
  <img src="Images/T3.PNG" alt="Text for Query 3" width="1200">
</p>

<p align="center">
  4. Find all movies that have a synopsis that contains the word "dwarves" or "hobbit". <br> Code: <code>db.movies.find({$or:[{synopsis:{$regex:"dwarves"}}, {synopsis:{$regex:"hobbit"}}]})</code>
</p>
<p align="center">
  <img src="Images/T4.PNG" alt="Text for Query 4" width="1200">
</p>

<p align="center">
  5. Find all movies that have a synopsis that contains the word "gold" and "dragon". <br> Code: <code>db.movies.find({$and:[{synopsis:{$regex:"gold"}}, {synopsis:{$regex:"dragon"}}]})</code>
</p>
<p align="center">
  <img src="Images/T5.PNG" alt="Text for Query 5" width="1200">
</p>

## Deleting Documents

<p align="center">
  1. delete the movie "Pee Wee Herman's Big Adventure". <br> Code: <code> db.movies.deleteOne ({_id: ObjectId('68280f11172fdf11a7fdf6f0')})</code>
</p>
<p align="center">
  <img src="Images/D1.PNG" alt="Text for Query 5" width="600">
</p> 

<p align="center">
2. Delete the movie "Avatar". <br> Code: <code> db.movies.deleteOne ({_id: ObjectId('72280f91472fdf11a0fdf6f0')}) </code>
</p>
<p align="center">
  <img src="Images/D1.PNG" alt="Text for Query 5" width="600">
</p>

## Relationships

<p align="center">
Insert the following to <code>user</code> collection.<br>
Code: <code>db.users.insertMany([{ _id: 1, username: "GoodGuyGreg", first_name: "Good Guy", last_name: "Greg" }, { _id: 2, username: "ScumbagSteve", full_name: { first: "Scumbag", last: "Steve" } }])</code>
</p>

<p align="center">
  <img src="Images/User1.PNG" alt="User Insert" width="400"><br>
  After Insert Results:<br>
  <img src="Images/User1R.PNG" alt="User Insert Result" width="400">
</p>

<p align="center">
Insert the following documents into a <code>posts</code> collection.<br>
Code: <code>db.comments.insertMany([{ username: "GoodGuyGreg", comment: "Hope you got a good deal!", post: ObjectId("68282cda172fd1a7fdf6f2") }, { username: "GoodGuyGreg", comment: "What's mine is yours!", post: ObjectId("68282cec172fd1a7fdf6f6") }, { username: "GoodGuyGreg", comment: "Don't violate the licensing agreement!", post: ObjectId("68282cf0172fd1a7fdf6f7") }])</code>
</p>

<p align="center">
  <img src="Images/C1.PNG" alt="Comment Insert 1" width="400"><br>
  <img src="Images/C2.PNG" alt="Comment Insert 2" width="400">
</p>

<p align="center">
Insert the following documents into a <code>comments</code> collection.<br>
Code:<br> <code>
db.comments.insert({username:"GoodGuyGreg", comment:"Hope you got a good deal!", post:ObjectId("5ca0b7e96435f98b5901f463")});<br>
db.comments.insert({username:"GoodGuyGreg", comment:"What's mine is yours!", post:ObjectId("5ca0b9706435f98b5901f46a")});<br>
db.comments.insert({username:"GoodGuyGreg", comment:"Don't violate the licensing agreement!", post:ObjectId("5ca0b8766435f98b5901f467")});<br>
db.comments.insert({username:"ScumbagSteve", comment:"It still isn't clean", post:ObjectId("5ca0b8546435f98b5901f466")});<br>
db.comments.insert({username:"ScumbagSteve", comment:"Denied your PR cause I found a hack", post:ObjectId("5ca0b9256435f98b5901f469")});
</code>
</p>

<p align="center">
  <img src="Images/Post1-1.PNG" alt="Post Insert 1" width="400"><br>
  <img src="Images/Post1-2.PNG" alt="Post Insert 2" width="400"><br><br>
  Relational Afterwards:<br>
  <img src="Images/PostResult.PNG" alt="Final Relational Result" width="400">
</p>

## Query
<p align="center">
<strong>1. Find all users</strong><br><br>
<code>db.users.find().pretty()</code><br><br>
<img src="Images/RelationalQ1.PNG" alt="Query 1" width="400">
</p>

<p align="center">
<strong>2. Find all posts</strong><br><br>
<code>db.posts.find().pretty()</code><br><br>
<img src="Images/RelationalQ2.PNG" alt="Query 2" width="400">
</p>

<p align="center">
<strong>3. Find all posts authored by "GoodGuyGreg"</strong><br><br>
<code>db.posts.find({username: "GoodGuyGreg"})</code><br><br>
<img src="Images/RelationalQ3.PNG" alt="Query 3" width="400">
</p>

<p align="center">
<strong>4. Find all posts authored by "ScumbagSteve"</strong><br><br>
<code>db.posts.find({username: "ScumbagSteve"})</code><br><br>
<img src="Images/RelationalQ4.PNG" alt="Query 4" width="400">
</p>

<p align="center">
<strong>5. Find all comments</strong><br><br>
<code>db.comments.find().pretty()</code><br><br>
<img src="Images/RelationalQ5.PNG" alt="Query 5" width="400">
</p>

<p align="center">
<strong>6. Find all comments authored by "GoodGuyGreg"</strong><br><br>
<code>db.comments.find({username: "GoodGuyGreg"})</code><br><br>
<img src="Images/RelationalQ6.PNG" alt="Query 6" width="400">
</p>

<p align="center">
<strong>7. Find all comments authored by "ScumbagSteve"</strong><br><br>
<code>db.comments.find({username: "ScumbagSteve"})</code><br><br>
<img src="Images/RelationalQ7.PNG" alt="Query 7" width="400">
</p>

<p align="center">
<strong>8. Find all comments belonging to the post "Reports a bug in your code"</strong><br><br>
<code>db.comments.find({post: ObjectId("682862155750a49fa77b8e7b")})</code><br><br>
<img src="Images/RelationalQ8.PNG" alt="Query 8" width="400">
</p>
