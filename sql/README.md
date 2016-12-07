# Arden2ByteCode SQL Example

This example is also documented in the Arden2ByteCode wiki at: 
<https://github.com/PLRI/arden2bytecode/wiki/Using-Databases>


## Running the Example

To run this example, you need an SQL capable JDBC driver such as the [Xerial SQLiteJDBC driver](https://github.com/xerial/sqlite-jdbc/releases).

If you have downloaded the SQLite JDBC driver, you can use the following command to start Arden2ByteCode:

    $ arden2bytecode --cp <path-to-sqlite>\sqlite-jdbc-<version>.jar --db org.sqlite.JDBC --env jdbc:sqlite:person.sqlite -r sql-example.mlm

Note that first, you have to cd to the directory the MLM is in.

The following command-line switches are used:

+ **--cp**  
  Extend the classpath by the JDBC driver.
+ **--db**  
  Specify the Java class name of the JDBC driver
+ **--env**  
  Specify the execution environment and the JDBC connection URL at the same time. The connection URL in turn specifies the SQLite file name.
+ **-r**  
  Tell Arden2ByteCode to run the MLM directly after compilation.

  
## Using other SQL Engines

If you want to use MySQL or any other SQL capable database, 
you have to adjust the command line switches given above by
the appropriate driver .jar file, class name and JDBC 
connection URL.

Two `.sql` files to set up the table used in this example are supplied in this folder, one for SQLite and one for MySQL. For other databases you might have to adjust the data types and datetime expressions.

For MySQL the [MySQL Connector/J](https://dev.mysql.com/downloads/connector/j/) can be used as a JDBC driver. After you have downloaded the driver and set up a local MySQL database, you can use the following command to run the example:

    $ arden2bytecode --cp <path-to-connectorj>\mysql-connector-java-<version>-bin.jar --db com.mysql.jdbc.Driver --env "jdbc:mysql://127.0.0.1:3306/<database-name>?user=<username>&password=<password>" -r sql-example.mlm

