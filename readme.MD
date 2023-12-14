# Fake VKontakte API

## Overview

`Fake VKontakte` is a mock social networking service designed to build RESTful API with OpenAPI 3.0 specifications.

This API allows users to interact with core social networking features such as managing accounts, friendships, feeds, chats, and conversations.

Features

* `Account Management`: Users can create, retrieve, update, and delete their accounts.
* `Friendship Interactions`: Users can add and remove friends, and view their friends' list.
* `Feed Operations`: Users can post content to their feed, view their feed, and upload media to their posts.
* `Chat System`: The API supports creating chats, sending messages, and retrieving chat histories.
* `Conversations:` Users can engage in conversations, similar to direct messaging.

## Using the API

You can interact with the API using tools like Postman or cURL. The base URL for the API is <https://localhost:8080/api/v1>.

Example request to get an account by ID:

```shell
curl -X GET "https://localhost:80808/api/v1/accounts/{account_id}>" -H "accept: application/json"
```

## Requirements

### Functional

* web and mobile app support
* viewing the user profile;
* sending and reading messages in conversations and chats.
* viewing user conversations and chats;
* adding and removing friends;
* viewing the user's friends;
* viewing the user's status (online/last seen);
* publishing a post to the feed;
* viewing the feed of posts (*home and users)*;
* uploading media files (posts/conversations/chats);
* people search
* media search
* notifications to users for updates(for example a new post in group chat/feed)
* blacklists (users/communities/etc)
* authentication/authorization;
* user communications (e.g., chat messages) must be encrypted end-to-end to ensure privacy

### Non-functional

* DAU - 50000000
* The service is available worldwide
* Message size limit (characters) - 4096
* Message attachment size limit (bytes) - 9000
* Friends number limit - 10000
* Chat participants limit - 100
* Messages history limit - 5 years (1825 days)
* Media storage time limit - 5 years (1825 days)
* Average number of messages sent per day - 5
* Average number of messages read per day - 20
* Average number of attachments/media sent per day - 3
* Response time for message sending - 1 sec
* Response time for message receiving - 5 sec
* The system must adhere to TLS for data in transit and encryption standard(e.g., AES) for data at rest.
* The encryption process should not degrade system performance, with a maximum allowable latency increase of 5% during peak usage.
* The system must comply with data protection regulations (e.g., 152-ФЗ, GDPR, HIPAA)

### Resources calculation

| DAU (million)                                    | 50,000,000    |
| ------------------------------------------------ | ------------- |
| Message size limit (characters)                  | 1,024         |
| Message attachment size limit (bytes)            | 5,242,880     |
| Friends number limit                             | 10,000        |
| Chat participants limit                          | 100           |
| Messages history time limit (days)               | 1,825         |
| Media storage time limit (days)                  | 1,825         |
| Average number of messages sent per day          | 5             |
| Average number of messages read per day          | 20            |
| Average number of attachments/media sent per day | 3             |
| Response time for message sending                | 1 sec         |
| Response time for message receiving              | 5 sec         |
|                                                  |               |
| Messages RPS (read)                              | 11,574        |
| Messages RPS (write)                             | 2,894         |
| Media RPS (write)                                | 1,736         |
|                                                  |               |
| Traffic messages (read,mb/s)                     | 23            |
| Traffic messages (write, mb/s)                   | 6             |
| Traffic media (write, mb/s)                      | 8,681         |
|                                                  |               |
| Storage for media (Tb)                           | 1,305,342     |
| Storage for messages (UTF-8, Cyrillic) (Tb)      | 850           |
| Disks for media (16Tb)                           | 81,584        |
| Disks for messages (16Tb)                        | 53            |
|                                                  |               |
| Messages per day (write)                         | 250,000,000   |
| Data size per message (bytes, UTF-8, Cyrillic)   | 2,048         |
| Total data size per day (mb)                     | 488,281       |
|                                                  |               |
| Messages per day (read)                          | 1,000,000,000 |
| Data size per message (bytes, UTF-8, Cyrillic)   | 2,048         |
| Total data size per day (mb)                     | 1,953,125     |
|                                                  |               |
| Media per day (write)                            | 150,000,000   |
| Data size per media (bytes)                      | 5,242,880     |
| Total data size per day (mb)                     | 750,000,000   |
|                                                  |               |
| Magic number (seconds in a day)                  | 86,400        |


## Documentation

For detailed API documentation, please refer to the [OpenAPI Specification](api/rest_api.yml).

## License

This project is licensed under the Apache 2.0 License - see the LICENSE file for details.

## Contact

For any queries or further information, please contact us at <fake@gmail.com>.
