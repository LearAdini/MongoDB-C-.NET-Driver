# MongoDB - C#.NET Driver
This is a project I made to create a user into MongoDB under the database I made "Address_Book" and in "users" collection.
You can view All users in the data base, You can view all users from certain city and view certain user

![0](https://user-images.githubusercontent.com/80118008/130597116-1fe4f9f1-8342-477c-816b-5ba03d5182a5.PNG)

# Insert Record
![AddUser](https://user-images.githubusercontent.com/80118008/130600930-20ae7c73-c0e7-4da9-9d48-b8e60f08210e.gif)


The InsertRecord function is a generic function that contains the collection name users as "table" and a generic record which will return a new Person object.

![InsertRecrodMethod](https://user-images.githubusercontent.com/80118008/130597896-6a6cc8c0-4b59-4af0-beb6-1e20ea424b19.PNG)

Now in Program I create a new instance of MongoDBCRUD and call it db,it should contain the Mongo database name(implemented inside MongoDBCRUD ctor) which is "Address_Book" and it should contain some object becasue the method demands some generic object so I give it a new instance of Person and give it all its neccessary via each text box text , created a new guid id([BsonId]) for the new user and a new Primary_Address instance which will have the Address info.

![InsertRecrodButton](https://user-images.githubusercontent.com/80118008/130598914-7f62376b-21e8-44b1-a2c2-21b58ab5053d.PNG)

# Load Records
![viewUsers](https://user-images.githubusercontent.com/80118008/130600612-14b2a015-2338-43e0-8247-bd7efa265d1f.gif)

The LoadRecords function will return a generic List and should contain the "table" name which is the users collection inside the database.
I create a variable called collection which is using the private IMongoDatabase db; object and get the collection by the "table" name.
Here I use the OptionBuilders which can help alot when deploying a query is neccessary.
And return the variable collection and find by the option builder variable to List.

![LoadRecordsMethod](https://user-images.githubusercontent.com/80118008/130599696-cd646b11-1fdd-4ebb-9244-de9faafb5ba1.PNG)

In Program I again create the db instance from MongoDBCRUD and create a new List which will contain <Person> called "persons", and will be equal to db instance LoadRecords function and receive the generic value as <Person>.In the bracket I asked for the "table" name so i give it the "users" collection.
To show all the users I tell the data grid view that its DataSource is the persons instance.
When the "VIEW USERS" button is clicked ti will try to load all the records from the db into the DGV.
  

![LoadRecordsButton](https://user-images.githubusercontent.com/80118008/130600856-58d56bb0-d3a7-4a53-9e86-2736bfe81818.PNG)

  

  



