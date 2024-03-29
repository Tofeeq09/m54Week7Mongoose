# REST API for Book Management

This project, which is an assignment for week 7 of the CodeNation software development boot-camp, implements a REST API using Express.js and MongoDB, with Mongoose as the ODM. The API allows users to perform CRUD operations on a collection of books stored in the database.

In a REST API, CRUD operations map to HTTP verbs as follows:

- **Create**: This operation is used to create a new resource. It corresponds to the POST HTTP verb. In this API, it is used to create a new book.

- **Read**: This operation is used to retrieve a resource. It corresponds to the GET HTTP verb. In this API, it is used to get the details of a book or to list all books.

- **Update**: This operation is used to update a resource. It corresponds to the PUT or PATCH HTTP verb. In this API, it is used to update the details of a book.

- **Delete**: This operation is used to delete a resource. It corresponds to the DELETE HTTP verb. In this API, it is used to delete a book.

## Project Structure

This project is structured to create a REST API (Representational State Transfer Application Programming Interface) using the Express.js framework, MongoDB for the database layer, and Mongoose as the Object Data Modeling (ODM) tool. Here are the details:

- **`src/controllers`**: This directory contains all the controller files. Each controller corresponds to a specific route and contains the logic for handling requests and responses. The controllers interact with the models to create, read, update, and delete resources in the MongoDB database.

- **`src/models`**: This directory contains all the database models. Each model defines the structure of a document in the MongoDB database. These models are used by Mongoose to interact with the MongoDB database in an object-oriented way.

- **`src/routes`**: This directory contains all the route files. Each route file defines the endpoints for a specific part of the API (e.g., `/books`). The routes map HTTP verbs and URLs to controller functions.

- **`src/app.js`**: This is the main application file. It sets up the Express.js application, connects to the MongoDB database using Mongoose, and includes all the routes. This file is the entry point of the application.

- **`test`**: This directory contains all the test files. Each test file tests a specific part of the application. These tests ensure that the API behaves as expected and help catch any regressions.

- **`.env`**: This file contains environment variables, such as the MongoDB connection string. It is not included in the Git repository for security reasons. These environment variables are used to configure the application, for example, by providing the URL to the MongoDB database.

## Dependencies

This project uses the following external dependencies:

- `dotenv`: A zero-dependency module that loads environment variables from a `.env` file into `process.env`.
- `express`: A fast, un-opinionated, minimalist web framework for Node.js.
- `mongoose`: A MongoDB object modeling tool designed to work in an asynchronous environment

### Installation

To install these dependencies, follow these steps:

1. Open your terminal.
2. Navigate to the project directory.
3. Run the following command:

```sh
npm install
```

## Environment Variables

This project uses the following environment variables:

- `MONGO_URI`: The connection string for the MongoDB database.

The Express.js server is configured to run on port 5000 by default. If port 5000 is already in use on your machine, you will need to change the port number in the server configuration.

You can set the `MONGO_URI` variable in a `.env` file in the root directory of the project. Here's an example of what the `.env` file might look like:

```env
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.mongodb.net/myDatabase
```

## Endpoints and Operations

### Adding a Book

- **Route:** `POST /books`
- **Description:** Adds a new book to the database.

### Fetching All Books

- **Route:** `GET /books`
- **Description:** Retrieves all books from the database.

### Deleting All Books

- **Route:** `DELETE /books`
- **Description:** Deletes all books from the database.

### Operations on Books by Title

- **Route:** `GET /books/title`
- **Description:** Fetches all unique titles from the database.
- **Route:** `GET /books/title/:title`
- **Description:** Fetches books from the database by their title.
- **Route:** `PUT /books/title/:title`
- **Description:** Dynamically update any field of a book by its title.
- **Route:** `DELETE /books/title/:title`
- **Description:** Deletes a book from the database by its title.

### Operations on Books by Author

- **Route:** `GET /books/author`
- **Description:** Fetches all unique authors from the database.
- **Route:** `GET /books/author/:author`
- **Description:** Fetches books from the database by their author.
- **Route:** `PUT /books/author/:author`
- **Description:** Updates books in the database by their author.
- **Route:** `DELETE /books/author/:author`
- **Description:** Deletes books from the database by their author.

### Operations on Books by Genre

- **Route:** `GET /books/genre`
- **Description:** Fetches all unique genres from the database.
- **Route:** `GET /books/genre/:genre`
- **Description:** Fetches books from the database by their genre.
- **Route:** `PUT /books/genre/:genre`
- **Description:** Updates books in the database by their genre.
- **Route:** `DELETE /books/genre/:genre`
- **Description:** Deletes books from the database by their genre.

### Operations on a Single Book by ID

- **Route:** `GET /books/:id`
- **Description:** Fetches a single book from the database by its ID.
- **Route:** `PUT /books/:id`
- **Description:** Dynamically update a book in the database by its ID.
- **Route:** `DELETE /books/:id`
- **Description:** Deletes a book from the database by its ID.

## Usage

To use this API, clone the repository and install the dependencies. Make sure to have MongoDB running locally or provide a connection URI. The server is configured to run on port 5000 by default. If port 5000 is already in use on your machine, you will need to change the port number in the server configuration.

```bash
git clone https://github.com/Tofeeq09/m54-Week7-Mongoose.git
cd m54-Week7-Mongoose
npm install
```

Then, start the server:

```bash
npm start
```

The API will be available at `http://localhost:5000` (or whatever port you have configured).

## Testing

This project uses [Thunder Client](https://www.thunderclient.io/) for testing API endpoints. Thunder Client is a lightweight, fast, and flexible HTTP client testing tool built into Visual Studio Code.

To test the API:

1. Open the project in Visual Studio Code.
2. Install the Thunder Client extension if you haven't already.
3. In the Thunder Client panel, click on "New Request".
4. Set the method and URL according to the endpoint you want to test.
5. If the endpoint requires a body or headers, set them in the "Body" or "Headers" tab.
6. Click "Send" to send the request and see the response.

You can also create collections of requests to group related endpoints together. This can be useful for testing different parts of the API.

Please note that some endpoints may require authentication. In this case, you will need to include a valid JSON Web Token in the "Authorization" header of the request.

## Contributing Guidelines

We welcome contributions from everyone. Here are some guidelines to follow:

1. Fork the repository: Click the "Fork" button at the top right of this repository to create your own copy.

2. Clone your fork: Use `git clone https://github.com/<your-username>/<repository-name>.git` to clone your fork to your local machine.

3. Create a branch: Use `git checkout -b <branch-name>` to create a new branch for your changes.

4. Make your changes: Add, edit, or delete files as necessary.

5. Commit your changes: Use `git add .` to stage your changes, `git commit -m "<commit-message>"` to commit them, and `git push origin <branch-name>` to push them to your fork.

6. Submit a pull request: Go to your fork on GitHub and click the "New pull request" button. Select your branch from the dropdown menu, and click "Create pull request".

Please make sure your code follows our style guidelines and passes all tests before submitting a pull request. We also recommend including a detailed description of your changes when you submit a pull request.

Thank you for your contributions!

## Task Requirements

### Tasks for the Assignment

- Create a Mongoose application that connects to a MongoDB database.
- Create the following routes:
  - POST: Adds a book to the database
  - GET: Gets all books from the database
  - PUT: Updates a book's author
  - DELETE: Deletes a single book from the database
- Separate the application into server/model/routes/controllers.

### Stretch Goals

- Create additional routes for:
  - Dynamically updating fields based on a book name
  - Deleting all entries from the database
  - Finding a single book by title
- Research and implement `req.params` for route parameters.

## Additional Notes

This project extends beyond basic CRUD operations and HTTP verbs and includes additional functionalities such as searching and updating books dynamically.

For further details on the project and its implementation, refer to the codebase and comments within the repository.

For assessment purposes, users are advised to utilize the `marking` branch, where comments have been omitted to improve visual clarity and ease of evaluation.
