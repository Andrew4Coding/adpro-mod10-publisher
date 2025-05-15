Name    : Andrew Devito Aryo

NPM     : 2306152494

Class   : ADVPROG - A


# Module 10 - Publisher - Reflection
### a. How much data your publisher program will send to the message broker in one run? 
The publisher program sends five messages to the message broker in one run. Each message contains a `UserCreatedEventMessage` struct with two fields: `user_id` (a `String`) and `user_name` (a `String`). 

Assuming the size of each string is determined by its content, the approximate data sent per message can be calculated as follows:
- `user_id`: 1 character (e.g., "1") = 1 byte.
- `user_name`: Length of the string (e.g., "2306152494-Amir") = 15 bytes.

For each message, the total size is approximately 1 byte (`user_id`) + 15 bytes (`user_name`) = 16 bytes.

Since there are 5 messages, the total data sent in one run is:
5 messages × 16 bytes = **80 bytes**.

### b. The url of: `“amqp://guest:guest@localhost:5672”` is the same as in the subscriber program, what does it mean?
The URL `“amqp://guest:guest@localhost:5672”` is the connection string used by both the publisher and subscriber programs to connect to the RabbitMQ message broker.


### Proof of Running RabbitMQ
![alt text](image.png)

### Console Logs in Publishing Events
![alt text](image-1.png)

Based on the image, the publisher program successfully published 5 messages to the RabbitMQ message broker. The messages were sent to the "user.created" exchange, and the program confirmed that each message was published successfully.

### Monitoring Chart (Before Uncomment Thread Sleep)
![alt text](image-3.png)

Based on the image, the monitoring shows the number of messages published to the RabbitMQ message broker. The chart indicates that the publisher program is sending messages at a consistent rate, with no significant spikes or drops in the number of messages published over time.