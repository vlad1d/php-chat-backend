# PHP Chat API

## Description
This project is a simple chat application backend written in PHP. It allows users to create chat groups, join these groups, and send messages within them. Additionally, it also implements a few extra basic commands to ensure the functionality of the application. The data is stored in a SQLite database.

## Running the Application

## Prerequisites
- PHP 8.3
- Composer
- SQLite3

⚠️ This project is created and tested on PHP 8.3. PHP 8.4 introduces deprecation warnings in dependencies that may affect runtime output. For the best experience, please use PHP 8.3 or lower.

## Running
```bash
cd php-chat-backend
composer install # to install the dependencies
composer run start
```
After that, open `http://localhost:8080` in your browser. 

Run this command in the application directory to run the test suite

```bash
composer run test
```

## Functionality

### Requirements
I used curl to make requests to the API. The following commands satisfy the requirements:
- [x] Creating chat groups:
```
curl -X POST 'http://localhost:8080/chats/{id}'
```
- [x] Join chat groups:
    
```
curl -X POST 'http://localhost:8080/chats/{chatId}/users/{userId}'
```
- [x] List all messages in a chat group (important: the userId here is only for verification - to check whether they are in the group; this command lists all messages in a chat group):

```
curl -X GET 'http://localhost:8080/messages/{chatId}/users/{userId}'
```

- [x] Send messages to a chat group:

``` 
  curl -X POST http://localhost:8080/messages/{chatId}/users/{userId} \
     -H "Content-Type: application/json" \
     -d '{"content": "Hello, world!"}'
```

### Additional Features
All routes are defined in the `routes.php` file. Additional implemented routes are:
- [x] Users: Get a list of users, get a user by id, create a new user.
- [x] Chats: Get a list of chats, get a chat by id, delete a chat, leave a chat.

### Further Improvements
The application could be improved by adding more features such as:
- [ ] User authentication
- [ ] User roles
- [ ] Message editing/deletion

## Contact
    Vlad Ichim | 0681097927 | vladichim17@yahoo.ro
