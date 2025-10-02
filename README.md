
## API Description

The API is deployed in root path /api
There are two main “routes”: /api/todo and /api/auth.

### The “todo” API has methods for:
- Get all todos 
- Add a todo 
- Get a todo by Id
- Get a todo by Category
- Update a todo (requires auth token)
- Delete a todo (requires auth token)

### The "auth" API has a method for:
- Sign in a user
- Register a user

I have implemented a JWT token strategy to secure the update and delete of "todos”.


## How to use

First the user has to be created using an email and a password (make a POST request to /api/ath/register passing anb object with "email" and "password").
The password is hashed when stored in database.
Then the user signs in using email and password making a POST request to /api/auth/login.
If it’s ok a JWT token is returned.
This JWT token is needed to make a PUT or DELETE request to /api/todo.
To get all todos by id or category there is no need to pass a JWT token, you can simply make a GET request to /api/todo/:id or /api/todo/:category.

## Testing

I have included a minimal e2e testing with supertest for the "todo" route in the backend folder. You can test it also with "Postman" or other tool to make HTTP requests.

## Technologies Used

- **Node.js**
- **Express.js**
- **MongoDB**
- **Mongoose**
- **Jest**
- **Supertest**
- **ESLint**
- **Prettier**
- **dotenv**

---

# Note to Reviewer

This project does not fully meet all the assignment requirements. I was able to implement the **auth** and **todo** APIs with JWT authentication, password hashing, and basic CRUD operations, along with minimal e2e testing.

What I **could not complete due to time constraints**:

* Full **NestJS + Nx Monorepo** structure (I used Express instead).
* Role-based authorization (ADMIN vs USER).
* **Analytics module** for tasks.
* **Docker + Cosmos DB emulator** setup and DevOps workflow.
* Comprehensive **unit + integration tests**.
* Bonus features like **Swagger docs, CI, rate limiting, pagination**.

Reason:
I am **new to NestJS**, and since I had only about half a day (including a public holiday), I focused on the core features first. I spent time learning from documentation, which helped me grasp how NestJS modules, guards, and strategies are structured.

Despite not completing everything, I learned a lot during this exercise and I’m confident that, with a bit more time, I could have implemented the remaining requirements. I enjoy working with new technologies and this was a valuable learning experience.

---
