   # MONGO COMMANDS


___
 ## 1. For creating a document./////////part of first operation CREATE


   use Name of document.//////for example.... use test

   [use is the keyword here and test is the name of document].
    - use is also used to shift to an already existing document.   
___
 ## 2. Inserting in a document.

    - insertOne clause.
        DATA IS ALWAYS STORED AS A BSON object.

        Therefore, assume an already existing document [test].

        db.test.insertOne({name:"Joey",Gender: "man", I'd: 3298165479623})

    - insertMany clause. 
        It just appends the insertOne clause and its work.

            -db.test.insertMany({name:"amy",Gender: "female", I'd: 3298352479623},{name:"sheldon",Gender: "male", I'd: 4364365479623})
___
## 3. To check if any data exist.
       
       - db.nameofdocument.find()
       - db.test.find()///example.....
___
## 4. show dbs ////It will show all the databases present.
      sample output: 
       config()
       data()
       test()

   - show collections [It will show all the documents present in a collection]

   - quit() [IN order to quit MONGO shell]
   

____
# Moving to querying and CRUD operations in MONGO DB.

## SOME BASIC symbol/expressions.

 >1. lte = less than or equal to.
 >2. lt = less than.
 >3. gt = greater than.
 >4. gte = greater than or equal to.
 >5. or /// for or joined queries.__

    MONGO DB queries for reading data.

     Taking example of test document we created before.

      Reading is achieved by using filter objects. 

    -db.test.find({I'd:{$gt:4000}}) //////  Here $ is a built in operator in mongo and used for comparison.

### gte,lte and lt can be used accordingly.

- for comparison in OR condition.
    
      db.test.find({$or:[{I'd:{  $lt:100000000000000000   } },
                           {I'd: { $gt : 1 } }   ] } )


___
# UPDATING DOCUMENTS

 ## 1. updateOne clause.
 ## 2. updateMany clause. 
 ## 3. replaceOne clause. 
 ## 4. replaceMany clause.

    - db.test.updateOne( { name:"Joey" } , { $set: {I'd:47476545678}  }  )
  
 ~~updateMany can be used accordingly.~~ 

 replaceOne and replaceMany can be used exactly like updateOne and updateMany.




# DELETING DOCUMENTS   

  ## 1. deleteOne 
  ## 2. deleteMany

    - db.test.deleteOne({name:"amy"})
    for deleting the first value that comes while scanning.

    - db.test.deleteMany({name"Sheldon"})
    for deleting all name values which have name as Sheldon.
