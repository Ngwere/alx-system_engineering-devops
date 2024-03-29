# Simple Web Design

![Simple Design](https://github.com/Ngwere/alx-system_engineering-devops/blob/master/task-0-WID.jpg.png)

## Description
   In this task, I presented the design that shows how the client called "User" connect to the host server hosting the website www.foobar.com. In this design, we do not use firewalls nor ssl certificates for protecting server's network. All components(database, application server) has to share the resources (CPU, RAM, and SSD) provided by the server. 

## Specifics About The Infrastructure
* What is a server?
  A server is a computer hardware or software that provides services to other computers, which are usually referred to as clients.

* What is the role of the domain name?
  To provide a human-friendly alias for an IP Address. For example, the domain the user typed www.foobar.com as the alias and the DNS server responded by mapping it to it's IP address 8.8.8.8

* What is the type of DNS record www is in www.foobar.com?
  www.foobar.com uses an A record. This can be checked by running dig www.foobar.com.
Note: the results might be different but for the infrastructure in this design, an A record is used.
Address Mapping record (A Record)—also known as a DNS host record, stores a hostname and its corresponding IPv4 address.

* What is the role of the web server?
  The web server is the software/hardware that accepts requests via HTTP or secure HTTP (HTTPS) and responds with the content of the requested resource or an error messsage that the user input.

* What is the role of the application server?
  The application server installs, operates and hosts applications and associated services for end users, IT services and organizations and facilitates the hosting and delivery of high-end consumer or business applications.

* What is the role of the database?
  To maintain a collection of organized information that can easily be accessed, managed and updated

* What does the server uses to communicate with the client?
  The user/client communicate with the server using the TCP/IP protocol suite

## Issues With This Infrastructure

* There are multiple SPOF (Single Point Of Failure) in this infrastructure.
For example, if the there is an issue with the application file the whole site would be down.

* Downtime when maintenance needed.
When we need to run some maintenance on any component, they have to be put down or the server has to be turned off. Since there's only one server, the website would be experiencing a downtime.

* Cannot scale if there's too much incoming traffic.
It would be hard to scale this infrastructure becauses one server contains the required components. The server can quickly run out of resources or slow down when it starts receiving a lot of requests.
