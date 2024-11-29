##Basic Information
Group 52

Member:
Lai Tsz Tsun 13033609
Wan Cheuk Long 13852744
Yeung Chiu Yat 13138898

Application: Inventory Management System

## Cloud-based server URL
https://s381-project-gp52.onrender.com

##Inventory Management System

This is a simple inventory management system built using **Node.js**, **Express**, **MongoDB Atlas**, and **EJS**. The system allows users to perform CRUD operations (Create, Read, Update, Delete) on inventory items and includes authentication for secure access.

## Features
- User login and authentication
- Hashed password stored in the database.
- Add new inventory items
- View inventory items in a styled table
- Edit existing inventory items
- Delete inventory items
- RESTful API endpoints for programmatic access
- Deployed using modern web technologies

## Running the Application
Start the Server:
- node server.js
- Access the Application:
- Open your browser and navigate to http://localhost:3000

## Create a User for the application
node server.js
---
curl -X POST http://localhost:3000/api/users \
-H "Content-Type: application/json" \
-d '{"username": "Sample", "password": "Sample"}'

## Project file intro
1. server.js
- Description: The main entry point of the application.

Functionality:
- Sets up the Express server.
- Connects to the MongoDB database using Mongoose.
- Handles routing for user authentication and CRUD operations for inventory items.
- Includes middleware for parsing JSON, managing sessions, and rendering EJS templates.
Example routes:
/login: Handles user login.
/inventory: Displays the inventory management page.
RESTful API routes for inventory: /api/inventory

---
2. package.json
- Description: Lists the project dependencies, metadata, and scripts.

Key Dependencies:
- bcrypt: For password hashing.
- body-parser: To parse incoming request bodies.
- cookie-session: To manage user sessions.
- dotenv: To handle environment variables.
- ejs: For rendering templates.
- express: Framework for creating server routes.
- mongoose: ODM for MongoDB.
Scripts:
"start": "node server.js": Command to start the server.

---
3. views (folder)
- Description: Contains EJS templates for the frontend UI.

Files Included:
- login.ejs: Template for the user login page.
- inventory.ejs: Template for managing and displaying inventory items.
- Shared partials like headers or footers (if applicable).

---
4. models (folder)
- Description: Contains Mongoose schemas for the database.

Files Included:
user.js:
- Defines the structure of the users collection in MongoDB.
- Fields: username, password (hashed).

item.js:
- Defines the structure of the inventory collection in MongoDB.
- Fields: name, quantity, price, category.

## Operation Guides
### Use of Login/Logout Pages
- Steps to Log In:
- Navigate to /login in your browser (e.g., http://localhost:3000/login or https://s381-project-gp52.onrender.com).
- Enter a valid username and password.
- Example credentials:
	Username: Admin
	Password: password
- Click the "Login" button.
- If login is successful, you are redirected to the inventory management page (/inventory).
- If login fails, an error message is displayed (e.g., "Invalid username or password").

Steps to Log Out:
- On the inventory page, click the "Logout" button (if available) or navigate to /logout.
- This destroys the session and redirects you back to the login page.

### Use of CRUD Web Pages
- Inventory Management Page (/inventory):

Create:
- Enter item details in the "Add New Item" form:
- Fields: Name, Quantity, Price, Category.
- Click the "Add Item" button.
- The new item appears in the inventory table.
---
Read:
- The inventory table displays all items in the database, with columns for Name, Quantity, Price, and Category.
---
Update:
- Click the "Edit" button next to the item you want to update.
- Modify the details in the form that appears and click "Update Item."
- The changes are reflected in the inventory table.
---
Delete:
- Click the "Delete" button next to an item.
- The item is removed from the inventory table.

## RESTful API Endpoints
Method: GET
- Endpoint: /api/inventory
- curl -X GET https://s381-project-gp52.onrender.com/api/inventory
- Description: Get all inventory items

Method: GET
- Endpoint: /api/inventory/:id
- curl -X GET https://s381-project-gp52.onrender.com/api/<id>
- Description: Get a specific item

Method: POST
- Endpoint: /api/inventory
- curl -X POST https://s381-project-gp52.onrender.com/api/inventory/ -H "Content-Type: application/json" -d '{"name": "Test Item", "quantity": 10, "price": 50, "category": "Test"}'
- Description: Add a new inventory item

Method: PUT
- Endpoint: /api/inventory/:id
- curl -X PUT https://s381-project-gp52.onrender.com/api/inventory/<id> -H "Content-Type: application/json" -d '{"name": "Updated Item", "quantity": 15, "price": 55, "category": "Updated Test"}'
- Description: Update an inventory item by ID

Method: DELETE
- Endpoint: /api/inventory/:id
- curl -X DELETE https://s381-project-gp52.onrender.com/api/inventory/<id>
- Description: Delete an inventory item by ID

##File Structure
├── views/
│   ├── login.ejs          # Login page template
│   ├── inventory.ejs      # Inventory page template
├── models/
│   ├── user.js            # User schema
│   ├── item.js            # Inventory item schema
├── server.js              # Main server file
├── package.json           # Project metadata and dependencies
├── README.md              # Project documentation

##Technologies Used
- Node.js: Backend runtime
- Express: Web framework
- MongoDB Atlas: NoSQL database
- Mongoose: MongoDB ODM
- EJS: Template engine
- cURL/Postman: For testing API endpoints
