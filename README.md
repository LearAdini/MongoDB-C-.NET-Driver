# MongoDB - C#.NET Driver
This is a project I made to create a user into MongoDB under the database I made "Address_Book" and in "users" collection.
You can view All users in the data base, You can view all users from certain city and view certain user

![0](https://user-images.githubusercontent.com/80118008/130597116-1fe4f9f1-8342-477c-816b-5ba03d5182a5.PNG)

# The Class's

**● MongoDBCRUD**

![crud0](https://user-images.githubusercontent.com/80118008/130603841-5332101a-44c3-49ec-8a76-4cfdc63b75ba.PNG)

**● Person**

![PersonClass](https://user-images.githubusercontent.com/80118008/130603881-3989f741-dea0-48d2-b92e-b4526e1f6b6f.PNG)
**● Address**

![AddressClass](https://user-images.githubusercontent.com/80118008/130603903-fe1b3a31-406b-4b1c-96ea-3cbcc85cdfa6.PNG)


# Insert Record
![AddUser](https://user-images.githubusercontent.com/80118008/130600930-20ae7c73-c0e7-4da9-9d48-b8e60f08210e.gif)


The InsertRecord function is a generic function that contains the collection name users as "table" and a generic record which will return a new Person object.

![InsertRecrodMethod](https://user-images.githubusercontent.com/80118008/130597896-6a6cc8c0-4b59-4af0-beb6-1e20ea424b19.PNG)

Now in Program I create a new instance of MongoDBCRUD and call it db(I could create it as a private instance but I do it as that for the example...),it should contain the Mongo database name(implemented inside MongoDBCRUD ctor) which is "Address_Book" and it should contain some object becasue the method demands some generic object so I give it a new instance of Person and give it all its neccessary via each text box text , created a new guid id([BsonId]) for the new user and a new Primary_Address instance which will have the Address info.

![InsertRecrodButton](https://user-images.githubusercontent.com/80118008/130598914-7f62376b-21e8-44b1-a2c2-21b58ab5053d.PNG)

# Load Records
![viewUsers](https://user-images.githubusercontent.com/80118008/130600612-14b2a015-2338-43e0-8247-bd7efa265d1f.gif)


The LoadRecords function will return a generic List and should contain the "table" name which is the users collection inside the database.
I create a variable called collection which is using the private IMongoDatabase db; object and get the collection by the "table" name.
Here I use the OptionBuilders which can help alot when deploying a query is neccessary.
return the variable collection and find by the option builder variable to List.

![LoadRecordsMethod](https://user-images.githubusercontent.com/80118008/130599696-cd646b11-1fdd-4ebb-9244-de9faafb5ba1.PNG)

In Program I again create the db instance from MongoDBCRUD and create a new List which will contain <Person> called "persons", and will be equal to db instance LoadRecords function and receive the generic value as <Person>.In the bracket I asked for the "table" name so i give it the "users" collection.
To show all the users I tell the data grid view that its DataSource is the persons instance.
When the "VIEW USERS" button is clicked ti will try to load all the records from the db into the DGV.
  

![LoadRecordsButton](https://user-images.githubusercontent.com/80118008/130600856-58d56bb0-d3a7-4a53-9e86-2736bfe81818.PNG)
  
 # Load Records via City Name
 ![ViewCity](https://user-images.githubusercontent.com/80118008/130602276-f9586c2b-5077-4605-8127-9e61bd277905.gif)

  
 The LoadRecordsByCity function will return A generic List and should contain the "table" name and an Address object.
 In the Builder I give it the Person class and start working on filtering.
 So I say that the variable filter is equal to Primary_Address.City which is given by the lambada expression and the value is the city object from Address.
return the variable collection and find by the filter that I made.
  
![LoadRecordsByCityMethod](https://user-images.githubusercontent.com/80118008/130601779-afd146e8-9647-486c-8cc5-2bc54a0850aa.PNG)
  
In the Program Create db instance from MongoDBCRUD and give it the database name.Create A List using <Person> call it p and should be equal to LoadRecordsByCity function from db instance,receive the generic value as <Person> and say that table is "users" and where the Address object should be I create a new Address and say that the City is equal to the name that was written in the textbox to find all user by the city name.
  
 ![LoadRecordsByCityButton](https://user-images.githubusercontent.com/80118008/130602174-d0cec91d-82c1-46f1-bc99-c5e5b4e943c9.PNG)
  
 # Load Records via User Name
 ![ViewOneUser](https://user-images.githubusercontent.com/80118008/130602437-cc2521f2-e570-40a6-8204-2dbdd94c20ca.gif)

  
 The LoadRecordsByName function will return A generic List and should contain the "table" name and the first name of the user(Just for the demonstration).
 In the Builder I give it a generic value and say that its equal to "First_Nane" which means it will go to the collection and select what ever the string is
 and the value is "name".
 return the variable collection and find by the filter that I made.
  
 ![LoadRecordsByNameMethod](https://user-images.githubusercontent.com/80118008/130603145-6ba54aff-89be-4a70-8e16-b1ee6402c07c.PNG)
  
  In Program Create db instance again Create A List using <Person> call it p and should be equal to LoadRecordsByName function from db instance,receive the       generic value as <Person> and say that table is "users" and where the users first name is equal to the textbox text that was given by the user.
  
  ![LoadRecordsByNameButton](https://user-images.githubusercontent.com/80118008/130603671-bd87bca7-4b53-4342-85bf-52b20ef23753.PNG)

# Inside MongoDB Compass
  ![Mongoshusers](https://user-images.githubusercontent.com/80118008/130604195-3884144c-7453-4c17-a6b2-f66db3db3b6f.PNG)
  ![Mongoshusers2](https://user-images.githubusercontent.com/80118008/130604218-42f9a683-83b2-4da9-92b5-c9d16ed52c5d.PNG)





  

  



