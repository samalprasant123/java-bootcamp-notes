# Session - 2 Notes

## Application Architecture

Application architecture generally comprises of many tier. We will discuss a three tier architecture. A three tier architecture comprises of the below tiers:
- Presentation tier : the user interface 
- Application tier : where request/data is processed
- Data tier : associated data is stored and managed

![3-tier-architecture](assets/3-tier-architecture.png)

#### Presentation tier

The presentation tier is the user interface and communication layer of the application, where the end user interacts with the application. Its main purpose is to display information to and collect information from the user. This top-level tier can run on a web browser or as a desktop application.

The content can be static or dynamic, and is usually developed using HTML, CSS and Javascript.

E.g.: an ecommerce site where the user adds products to the shopping cart, adds payment details or creates an account

#### Application tier

The application tier, also known as the logic tier or middle tier, is the heart of the application. In this tier, information collected in the presentation tier is processed - sometimes against other information in the data tier - using business logic (a specific set of business rules). The application tier can also add, delete or modify data in the data tier.

The application tier is typically developed using Java, Python, Perl, PHP or Ruby, and communicates with the data tier using API calls.

E.g.: To continue the ecommerce example, this is the tier that queries the inventory database to return product availability, or adds details to a customer's profile. 

#### Data tier

The data tier, sometimes called database tier, data access tier or back-end, is where the information processed by the application is stored and managed. This can be a relational database management system such as PostgreSQL, MySQL, MariaDB, Oracle, DB2 or Microsoft SQL Server, or in a NoSQL Database server such as Cassandra, CouchDB or MongoDB. 

In a three-tier application, all communication goes through the application tier. The presentation tier and the data tier cannot communicate directly with one another.

## Working of a Web request

