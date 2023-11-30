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

## Documentation

For detailed API documentation, please refer to the [OpenAPI Specification](api/rest_api.yml).

## License

This project is licensed under the Apache 2.0 License - see the LICENSE file for details.

## Contact

For any queries or further information, please contact us at <fake@gmail.com>.
