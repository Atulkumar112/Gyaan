## Definations

### Redis

Redis is an open-source, in-memory data structure store that is often referred to as a data structure server. It is designed to be fast, lightweight, and highly scalable, making it ideal for use cases that require quick data access and caching. Redis is commonly used as a caching layer to improve the performance of applications and to store frequently accessed data in memory, reducing the need to fetch data from slower traditional databases.
Caching: Redis is commonly used as a caching layer to store frequently accessed data in memory, reducing the need to fetch data from slower databases.
Session Store: Redis can be used as a session store for web applications, where session data is stored in memory for quick access and retrieval.
Data Structures: Redis supports a wide range of data structures, such as strings, lists, sets, sorted sets, hashes, and more. Each data structure has its own set of commands that enable efficient data manipulation.


### RabbitMQ

RabbitMQ is a message broker that enables communication between different parts of a system by facilitating the exchange of messages between applications in a decoupled and asynchronous manner.

In NestJS, you can use RabbitMQ to implement message-based communication between different components of your application. NestJS provides a module called @nestjs/microservices that allows you to integrate RabbitMQ as a message broker easily.


### Beekeeper

Beekeeper Studio is a database manager and SQL GUI. It is a desktop app that is easy to use. It’s a visual alternative to command line tools like psql or mysql, while also providing a bunch of useful extra features.


### SQL-migrate

SQL-migrate is a tool and library that simplifies the process of managing and applying SQL database migrations. It is commonly used in software development to keep track of changes to the database schema over time and apply those changes to the database as the application evolves.

Migrations are scripts that define the changes to the database schema, such as creating or modifying tables, adding or removing columns, and altering indexes. SQL-migrate allows developers to define these changes in a structured and version-controlled manner, making it easy to share schema changes with the team and apply them consistently across different environments.


### Timescale Database

Timescale is a time-series database (TSDB) designed to handle large volumes of time-stamped data efficiently and effectively. It is an extension built on top of PostgreSQL, which means it benefits from PostgreSQL's powerful features while providing specialized functionality for time-series data.

Time-series data is a type of data that records values at different points in time, such as sensor readings, financial data, server metrics, and more. Time-series databases are optimized to handle data that is organized and queried based on timestamps.


### Adminer

Adminer is a free and open-source database management tool that allows users to interact with various database systems through a web-based user interface. It supports multiple database systems, including PostgreSQL, MySQL, SQLite, MS SQL, Oracle, and others.


### Encription (for login password security)

We can convert our password into the encripted format and then store it into the database we do that thing for more security. there are many techniques but two majar techniques are Encription and hashing. Hashing is more reliable and secure more then encription so we will use hashing.
Encription:- In the encription let suppose we have password like xyz so first we have to convert it into a key then this key will be encripted. and main disadvantage is that anyone (hacker) can discrepte it from encripted key to actual password. and we can lost our password.

- Hashing:- In the hashing let suppose we have password xyz and then we encripted it directly. and best advantage is it can't be decripted. we can do hashing with many algorithms but majar are two algorithms `md5` and bcrypted. md5 became old algo so right now we use bcripted. You can also try md5 in terminal just write in terminal (where is the package.json file/ or any other file which you want to encripted key) :- 
```bash
md5sum package.json"
``` 


