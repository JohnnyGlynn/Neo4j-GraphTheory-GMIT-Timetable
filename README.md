# Neo4j Graph Theory Database Project

### Preface
Initially I had planned to design a HTML page scraper in node.js and subsequently in Python. Unfortunately I ran into alot of errors getting these solutions off the ground so I decided it was best that I design the database by hand, although time consuming and difficult, I feel that I have recreated a Timetabling solutiong that could easily be scaled up from just one semester to and entire colleges timetableing database (Obviously not coded entirely by hand, but still), but in saying this, nothing is perfect and there is always going to be a better way of doing things.

### [Neo4j](https://neo4j.com/)
Neo4j is an Open source noSql graph database management system developed by Neo Technology, Inc. Neo4j is written in Java and uses its own querying language Cypher. Cypher can be accessed through a multitude of different languages, including scripting languages such as Python and javascript(ie Node).

### Cypher
Cypher is the querying language used in Neo4j, and bares a resembelance to that of SQL. An example of a Cypher query is 
```
MATCH (n) RETURN n LIMIT 50
```
This is a query I found myself using frequently as returned 65 nodes in my graph rather than the default limit of 25, allowing me to see everything within my graph.

### Components of a Graph Database
The 4 key components to a Graph database are Nodes, Labels, Relationships and Properties.

![picture](https://github.com/JohnnyGlynn/Neo4j-GraphTheory-GMIT-Timetable/blob/master/NEO4J-%20Relationship-and-Node-example.PNG "Graph Example")

#### Nodes

Nodes are essentially objects which can hold an attribute, similar to a key/value pair. They can be given labels and properrties to define exactly what they do, for instance in the above graph I have one of every node type:

Node | Label |
--- | --- |
 Department|Node to represent the department of the current timetable|
 Course|Node that represents the course within the department being timetabled|
 Lecturer|Nodes for the lecturers within that department, lecturing that course|
 Year|Year group of the course node|
 Group|Node for the class groups within the year of that course|
 Subject|Node to represent the modules thought by the lecturers in that course|
 Lab|Node to represent the Labs for the modules thought by the lecturers in that course|
 Timeslot|Time of Day nodes|
 Day|Nodes for the days of the week|

 These Nodes represent the main aspects of the time tabling system, Ive pretty much taken every physical aspect of the timetable and reacreated a node based on that aspect, ie Times, Lectures, Labs. In this case, theoretically you could replicate any time table into this setup, all you would have to do would be to fill in different values, and scale the amound of information required, there would be more lectures and labs, but time slots and days wouldn't change.

#### Labels

Labels are the names given to the nodes within the graph database, All of wich can be seen in the above table.

#### Relationships

Relationships are what link two or more nodes together, they can be uni or bi directional and can accurately describe why one node is linked to another, for example:

Node | Relationship | Node|
--- | --- | --- |
 Department|COURSE_WITHIN|Course|
 Year|YEAR_OF|Course|
 Year|ATTENDING|Timeslot
 Year|ATTENDS|Lecture
 Lecturer|TEACHES|Lab, Subject|
 Lecturer|MEMBER_OF|Department
 Lecturer|LECTURER_AS_PART_OF|Course
 Group|CLASS_OF|Year|
 Group|ATTENDING|Timeslot
 Group|ATTENDS|Lab
 Subject|SUBJECT_OF|Course|
 Subject|SCHEDULED_ON|Day|
 Subject|TIMED_FOR|Timeslot
 Subject|LAB_OF|Lab
 Lab|SCHEDULED_ON|Day|
 Lab|LAB_IN|Course
 Timeslot| FOLLOWED_BY|Timeslot|
 Day|TIME_OF_DAY|Timeslot|

 These relationships accurately describe why each node is liked to one another, making it easy to discern between both when analyzing the graph.

#### Properties

The Properties of the node are the unique data belonging to that node, specific data such as Department name : Computer Science and Applied Physics, and Lecturer name Ian McLoughlin

Node | Properties |
--- | --- |
 Department|Computer Science and Applied Physics|
 Course|Software Development|
 Lecturer|Ian McLoughlin|
 Year|3rd|
 Group|C|
 Subject|Graph Theory|
 Lab|Graph Theory Lab|
 Timeslot|9.00am, 9.30am, 10.00am, 10.30am|
 Day|Wednesday|

 Properties are the main component of storing useful data within the graph database its self.


 ### User guide

 To access my time tabling database, please first install [Neo4j](https://neo4j.com/) on you machine. Once you have Neo4j, download the [.graphdb]https://github.com/JohnnyGlynn/Neo4j-GraphTheory-GMIT-Timetable file, GMIT-TimeTable.graphdb, located in my repository. Once you have this file, open Neo4j. When Neo4j opens click on Choose, and navigate to where you have saved my .graphdb file. Select the file and press start on the Neo4j command window, The coloured bar at the bottom should be green, if so, navigate to Localhost:7474 in your browser. The database is open and you are ready to start querying.
 
 To start off use this command:
 ```
MATCH (n) RETURN n LIMIT 50
```
It will display every node and relationship on my database, That of which there are 48 nodes and 382 relationships in total



