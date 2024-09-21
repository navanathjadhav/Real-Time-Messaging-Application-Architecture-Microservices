# Real-Time Messaging Application Architecture (Microservices)

This project outlines the microservice architecture for building a scalable and highly available real-time messaging application, similar to Slack. The architecture is designed to handle a large number of concurrent users, provide efficient real-time messaging, and ensure fault tolerance.

## Give a Star ⭐

If you liked this project or found it helpful then please give it a star.
Thanks.

## Architecture diagram

![Here](<./Real-Time_Messaging_Application_Architecture_(Microservices).png>)

## Download

Get a [PDF version](<./Real-Time_Messaging_Application_Architecture_(Microservices).pdf>).

## User Interface

The User Interface (UI) layer is responsible for presenting the application's visual components to users and handling their interactions. It ensures a smooth and intuitive experience by providing an appealing and responsive interface.

## API Gateway

The API Gateway serves as a centralized entry point for client requests. It acts as a mediator between the client and the Micro Services, handling tasks such as request routing, security, protocol translation, and caching. The API Gateway simplifies client-side integration by providing a unified API interface and enhancing the overall performance, scalability, and security of the system.

### Service Registry using Consul

Consul is a service registry tool that enables automatic discovery and registration of microservices in a distributed system. It provides a centralized location for microservices to register their availability and health status. Consul allows other services to dynamically discover and communicate with these registered services, facilitating seamless service-to-service communication.

### Load Balancing using Nginx

Nginx is a powerful and widely-used web server, reverse proxy, and load balancer that efficiently distributes incoming traffic across multiple backend servers. As a load balancer, Nginx intelligently routes requests to different backend servers based on predefined algorithms (e.g., round-robin, least connections).

### Security using OAuth 2.0

OAuth 2.0 is an industry-standard authorization framework that enhances security in modern applications. It allows users to grant limited access to their protected resources to third-party applications without sharing their credentials. By using access tokens, OAuth 2.0 ensures that only authorized applications can access user data. This delegation of access helps prevent the exposure of sensitive information and enables seamless and secure authentication and authorization workflows in a variety of web and mobile applications.

### Caching using Redis

Redis is an in-memory data store that excels at caching, enhancing application performance by storing frequently accessed data in memory. With low-latency access times, Redis can quickly serve cached content, reducing the need to retrieve data from slower databases. Its versatility supports various data structures, making it suitable for caching not only simple key-value pairs but also more complex data like lists, sets, and sorted sets.

## Real-time Communication Layer

The Real-time Communication Layer is responsible for managing persistent, bi-directional communication channels using protocols like Socket.IO. It ensures low-latency interactions between clients and backend microservices by bypassing the traditional API Gateway, directly routing real-time data. This design allows for seamless communication, ideal for real-time chat, notifications, and status updates, ensuring minimal delays and high throughput, even during heavy loads.

## Micro Services

### Messaging Service using Golang

The Messaging Service handles the core functionality of real-time message transmission, including direct messaging, group chats, and channels. Built in Golang for high concurrency and performance, it ensures fast message delivery and storage. This service also supports message persistence, allowing users to retrieve past messages, even if they were offline, ensuring a smooth and reliable user experience across devices.

### User Management Service using Node

The User Management Service is responsible for user authentication, profile management, and session handling. Built using Node.js, it supports modern authentication protocols like OAuth and JWT, ensuring secure and scalable identity management. It also tracks user presence, managing online/offline status in real-time, which is critical for accurate messaging and notification systems in the application.

### File Management Service using Golang

The File Management Service efficiently manages the upload, storage, and retrieval of various file types, such as images, documents, and media files. Written in Golang for optimal performance, it integrates seamlessly with object storage services like AWS S3. The service ensures that file operations are secure, scalable, and capable of handling large volumes of data while maintaining performance.

### Notification Service using Node

The Notification Service handles the real-time delivery of various notifications, including in-app messages, push notifications, and email alerts. Implemented in Node.js, it leverages message queues like Kafka to asynchronously dispatch notifications, ensuring timely delivery even under high load. This service is essential for keeping users informed of important events, such as new messages or updates, without causing delays in the system.

### Search Service using Node

The Search Service provides powerful, full-text search capabilities across messages, files, and user profiles, enabling users to find content quickly and efficiently. Built in Node.js and powered by Elasticsearch, the service ensures distributed and scalable search operations. It handles large volumes of data, offering fast, real-time search responses even as the dataset grows, making it a critical feature for user productivity.

### Databases

#### User DB using PostgreSQL

The User Database is responsible for storing critical user information such as profiles, authentication credentials, and settings. Using PostgreSQL, it provides robust relational data management, ensuring data integrity and scalability. The database supports complex queries, ACID transactions, and is optimized for secure user data storage in a distributed environment.

#### Messaging DB using Cassandra

The Messaging Database is designed for write-heavy workloads, particularly the storage of chat messages. Built on Cassandra, it offers high availability, horizontal scalability, and fast write performance. This NoSQL database is optimized for real-time message storage, ensuring low-latency reads and writes, even in globally distributed systems, making it ideal for high-volume messaging applications.

#### File metadata DB using MongoDB

The File Metadata Database stores all metadata related to files, such as file type, size, timestamps, and access control information. Using MongoDB, a document-based NoSQL database, it allows for flexible schema design and high scalability. This ensures efficient storage and retrieval of file-related information, particularly in systems with a wide variety of file types and large-scale data.

#### Database Scaling

##### Shards

DB sharding is a horizontal database scaling technique that involves partitioning data across multiple servers or shards. Each shard holds a portion of the data, distributing the workload and improving performance. Sharding enables handling large data volumes and high user loads by parallelizing database operations.

##### Hash

DB hash is a technique used in database systems for distributing data across shards. It involves hashing a specific attribute or key of the data to determine which shard it belongs to. This ensures a more even distribution of data across the shards, preventing hotspots and balancing the workload.

##### Replica

DB replica is a database copy created from the primary database to provide redundancy and high availability. It helps improve fault tolerance by enabling data replication to multiple servers. Read operations can be offloaded to replicas, reducing the load on the primary database and improving read performance.

##### Index

DB index is a data structure that improves query performance by allowing faster data retrieval based on specific fields. It works like a lookup table, mapping indexed values to their corresponding storage locations in the database. Indexing reduces the need for full table scans, speeding up query execution.

## Share & Care

If you think this project is helpful share it on [Twitter](https://twitter.com/intent/tweet?url=https://github.com/navanathjadhav/Real-Time-Messaging-Application-Architecture-Microservices).

## Contribute

You are always welcome to help to make this project more knowledgeable and helpful for other developers.

Submit a PR.
