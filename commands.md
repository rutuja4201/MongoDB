# MongoDB commands for Database

to start mongo compass

open powershell and type mongo so that you can issue commands from your command line

``` 
mongo 
``` 


view all the databases
```
show dbs
```

create new database or switch to database
```
use <databaseName>
```

tells in which database you are working
```
db
```

to delete any database go into that db and type db.dropDatabase()
for eg.
- use <databaseName>  // switch to that db or create new db
- db  // check in which db you are working
```
db.dropDatabase()  // deletes the database in which you are working
```

---
  
# MongoDB commands for Collections

Show Collections
```
show Collections
```
  
create a collection
```
db.createCollection('<collectionName>')
```
  
delete collection
```
db.<collectionName>.drop()
```

---
  
# MongoDB commands for Rows

insert 1 row 
```
db.<collectionName>.insert({
    'name' : 'Rutuja',
    'lang' : 'JS',
    'member_since' : 5
})
```

insert many rows
```
db.<collectionName>.insertMany([{
    'name' : 'Rutuja',
    'lang' : 'JS',
    'member_since' : 5
},
{
    'name' : 'Tom',
    'lang' : 'C++',
    'member_since' : 15
},
{
    'name' : 'Terry',
    'lang' : 'JS',
    'member_since' : 2
},
{
    'name' : 'GB',
    'lang' : 'Python',
    'member_since' : 25
}])
```
  
view all rows in a collection
```
db.<collectionName>.find()
db.<collectionName>.find().pretty()  // shows all rows in prettified manner (i.e more readable format)
```
---
  
# Search in MongoDB

```
db.<collectionName>.find({lang:'Python'})  // it will return all the objects with lang:Python
```
  
limit command - will show only limited number of objects/rows 
- for eg.2
```
db.<collectionName>.find().pretty().limit(2)
```
  
count number of output rows
```
db.<collectionName>.find().count()
db.<collectionName>.find({lang:'Python'}).count()  // returns count of number of rows with lang Python
```
  
view rows in sorted order
```
db.<collectionName>.find().sort({name:1})  // returns rows in sorted order based on name - ascending order (1)
db.<collectionName>.find().sort({name:-1})  // returns rows in sorted order based on name - descending order (-1)
```
  
find One command - returns only one row
```
db.<collectionName>.findOne({name:'Rutuja'})
```
  
update a row
```
db.<collectionName>.update({name:'Rutuja'},
{
    'name' : 'Rutuja',
    'lang' : 'JS',
    'member_since' : 51  // updated this from 5 to 51
})
```
---
  
# Explore MongoDB operators from official doc on the site
eg. Rename operator, Increment operator

delete row
```
db.<collectionName>.remove({lang:'Python'})  // removes all rows with lang python
```
---

# Filters - less than, greater than

Less than
```
db.<collectionName>.find({member_since: {$lt: 90}})
```
  
Greater than
```
db.<collectionName>.find({member_since: {$gt: 90}})
```
  
- Less than -> $lt
- Greater than -> $gt
- Less than equal to -> $lte
- Greater than equal to -> $gte

---

- mongodb is fast
- secured
- you'll see all the data in compass

---
MongoDB Atlas

---
COH Blog post - https://www.codewithharry.com/blogpost/mongodb-cheatsheet/














