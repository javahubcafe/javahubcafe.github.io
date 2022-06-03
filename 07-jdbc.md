## Q.	What is JDBC ?

JDBC is an abstraction layer that allows users to choose between databases. JDBC enables developers to write database applica- tions in Java, without having to concern themselves with the underlying details of a particular database.

## Q.	Explain the role of Driver in JDBC.

The JDBC Driver provides vendor-specific implementations of the abstract classes provided by the JDBC API. Each driver must provide implementations for the following classes of the java.sql package:Connection, Statement, PreparedStatement, CallableStatement, ResultSet and Driver.

## Q.	What is the purpose Class.forName method ?

This method is used to method is used to load the driver that will establish a connection to the database.

## Q.	What is the advantage of PreparedStatement over Statement ?

PreparedStatements are precompiled and thus, their performance is much better. Also, PreparedStatement objects can be reused with different input values to their queries.

## Q.	What is the use of CallableStatement ? Name the method, which is used to prepare a CallableStatement.
A CallableStatement is used to execute stored procedures. Stored procedures are stored and offered by a database. Stored procedures may take input values from the user and may return a result. The usage of stored procedures is highly encouraged, because it offers security and modularity.The method that prepares a CallableStatement is the following: CallableStament. prepareCall();


## Q.	What does Connection pooling mean ?

The interaction with a database can be costly, regarding the opening and closing of database connections. Especially, when the number of database clients increases, this cost is very high and a large number of resources is consumed.A pool of database connections is obtained at start up by the application server and is maintained in a pool. A request for a connection is served by a connection residing in the pool. In the end of the connection, the request is returned to the pool and can be used to satisfy future requests.
 

## Q.	Explain Marshalling and demarshalling.

When an application wants to pass its memory objects across a network to another host or persist it to storage, the in-memory representation must be converted to a suitable format. This process is called marshalling and the revert operation is called demarshalling.

## Q.	Explain Serialization and Deserialization.

Java provides a mechanism, called object serialization where an object can be represented as a sequence of bytes and includes the object’s data, as well as information about the object’s type, and the types of data stored in the object. Thus, serialization can be seen as a way of flattening objects, in order to be stored on disk, and later, read back and reconstituted. Deserialisation is the reverse process of converting an object from its flattened state to a live object.
