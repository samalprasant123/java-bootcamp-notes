# Session - 2 Notes

## Application Architecture

Application architecture generally comprises of many tier. We will discuss a three tier architecture. A three tier architecture comprises of the below tiers:
- Presentation tier : the user interface 
- Application tier : where data is processed
- Data tier : associated data is stored and managed

![3-tier-architecture](assets/3-tier-architecture.png)

In a three-tier application, all communication goes through the application tier. The presentation tier and the data tier cannot communicate directly with one another. Client makes a request to the presentation tier and at first call static contents are served mostly. Subsequent requests might be served by the application tier, where business logic is executed and state is saved in database.

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

## Working of a Web request

All computers on the internet, from smart-phone or laptop to the servers that serve content, communicate with one another by using numbers. These numbers, known as IP addresses, are in one of the following formats:
- Internet Protocol version 4 (IPv4) format, such as 192.0.2.44
- Internet Protocol version 6 (IPv6) format, such as 2001:0db8:85a3:0000:0000:1b3d:0001:2345

When you open a browser and go to a website, you don't have to remember and enter a long string of characters like that. Instead, you can enter a domain name like example.com and still end up in the right place. A DNS service helps to make that connection between domain names and IP addresses.

![how-a-request-is-routed](assets/how-route-53-routes-traffic.png)

1. A user opens a web browser, enters www.example.com in the address bar, and presses Enter.

2. The request for www.example.com is routed to a DNS resolver, which is typically managed by the user's internet service provider (ISP), such as a cable internet provider, a DSL broadband provider, or a corporate network.

3. The DNS resolver for the ISP forwards the request for www.example.com to a DNS root name server.

4. The DNS resolver forwards the request for www.example.com again, this time to one of the TLD (top level domain) name servers for .com domains. The name server for .com domains responds to the request with the names of the four Route 53 name servers that are associated with the example.com domain.

5. The DNS resolver chooses a Route 53 name server and forwards the request for www.example.com to that name server.

6. The Route 53 name server looks in the example.com hosted zone for the www.example.com record, gets the associated value, such as the IP address for a web server, 192.0.2.44, and returns the IP address to the DNS resolver.

7. The DNS resolver finally has the IP address that the user needs. The resolver returns that value to the web browser.

8. The web browser sends a request for www.example.com to the IP address that it got from the DNS resolver. This is where your content is, for example, a web server running on an say Amazon EC2 instance or an Amazon S3 bucket that's configured as a website endpoint.

9. The web server or other resource at 192.0.2.44 returns the web page for www.example.com to the web browser, and the web browser displays the page.
