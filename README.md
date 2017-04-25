# Neo4j Graph Theory Database Project

### Preface
Initially I had planned to design a HTML page scraper in node.js and subsequently in Python. Unfortunately I ran into alot of errors getting these solutions off the ground so I decided it was best that I design the database by hand, although time consuming and difficult, I feel that I have recreated a Timetabling solutiong that could easily be scaled up from just one semester to and entire colleges timetableing database (Obviously not coded entirely by hand, but still), but in saying this, nothing is perfect and there is always going to be a better way of doing things.

### [Neo4j](https://neo4j.com/)
Neo4j is an Open source noSql graph database management system developed by Neo Technology, Inc. Neo4j is written in Java and uses its own querying language Cypher. Cypher can be accessed through a multitude of different languages, including scripting languages such as Python and javascript(ie Node).

### Cypher
Cypher is the querying language used in Neo4j, and bares a resembelance to that of SQL. An example of a Cypher query is 
```
MATCH (n) RETURN n LIMIT 65
```
This is a query I found myself using frequently as returned 65 nodes in my graph rather than the default limit of 25, allowing me to see everything within my graph.

### Components of a Graph Database
The 4 key components to a Graph database are Nodes, Labels, Relationships and Properties.

![picture](https://github.com/JohnnyGlynn/Neo4j-GraphTheory-GMIT-Timetable/blob/master/NEO4J-%20Relationship-and-Node-example.PNG "Graph Example")

#### Nodes
#### Labels
#### Relationships
#### Properties