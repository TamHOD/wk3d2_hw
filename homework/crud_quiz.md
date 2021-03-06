# CRUD Quiz

Use the solution to this afternoon's Property Tracker lab to answer the following questions. Please write your answers under each question, push the file to GitHub, and submit in the usual way.

## MVP Questions

In our Property Tracker application:

Q1. Where are we instantiating instances of the `Property` class?
console.rb, Property.rb

Q2. Where are we defining the SQL that enables us to save the ruby `Property` object into the database?
Property.rb in the save method.

Q3. In console.rb, which lines modify the database?
lines which include .save, .update and .delete(_all_).

Q4. Why do we not define the id of a `Property` object at the point we instantiate it (‘new it up’)?
The id is a property which is defined by the DB.

Q5. Where and how do we assign the id (that is generated by the database) to the ruby `Property` object?
In property.rb in the save function, by reading the id produced by the DB and assigning it to @id.

Q6. Why do we put a guard (an `if` clause) on the `@id` attribute in the constructor?
There might not be an id yet if the object hasn't been saved to the DB so this avoids errors.

Q7. Why are some of the CRUD actions represented by instance methods, and others by class methods?
Some methods need only be applied to a specific instance, such as update and delete, but others must look at/apply to every item such as find and delete_all.

Q8. What type of data structure is returned by calls to `db.exec_prepared()`? In the `save` method, how do we access the id from the returned data structure?
An array of hashes. @id = properties_hashes[0]['id'].

Q9. Why do we use prepared statements when performing database operations?
To avoid SQL injection attacks.

## Extension Questions

Look at the `find_by_id` and `find_by_address` methods in the `Property` class.

Q10. What do they take in as their arguments?
An id number and address string, respectively.

Q11. What are their return values?
An array containing the details of the property (or nil/[]).
