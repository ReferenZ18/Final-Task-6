# Final Task 6 - MongoDB Practice

In this task we utilize and learned the MongoDB program, Using the given guide step-by-step by our Instructor.

## MongoDB Database

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



## Relationships

