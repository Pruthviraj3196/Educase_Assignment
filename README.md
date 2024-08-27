# School Management API

This project is a Node.js and Express.js API that allows for the management of school data, including adding new schools and retrieving a list of schools sorted by proximity to a user-specified location. The project uses MySQL as the database to store school information.

## Features

- **Add School**: Add new schools with details such as name, address, latitude, and longitude.
- **List Schools**: Retrieve a list of all schools sorted by their proximity to a user-specified location (latitude and longitude).

## Postman Collection
A Postman collection is provided to easily test the APIs. You can import the collection by downloading it [here](assets/Educase.postman_collection.json)

## Hosting
The API is hosted on Render. You can access the live API at: https://educase-assignment-j3kq.onrender.com


## Technologies Used

- **Node.js**: JavaScript runtime for building the backend.
- **Express.js**: Web framework for Node.js.
- **MySQL**: Relational database for storing school data.
- **Postman**: Tool for testing APIs.

## Prerequisites

- **Node.js**: Install Node.js
- **MySQL**: Install MySQL and set up a database.

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/educase_school_management-api.git
cd educase_school_management-api
```

### 2.Install Dependencies

```bash
npm install
```
### 3.Set Up MySQL Database
 Create a new MySQL database:

 ```bash
CREATE TABLE school_management_system (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    address VARCHAR(255) NOT NULL,
    latitude FLOAT NOT NULL,
    longitude FLOAT NOT NULL
);
```

### 4.Run the Server
 ```bash
node server.js
```

## API Endpoints

### 1. Add School

- **Endpoint**: `/api/addSchool`
- **Method**: `POST`
- **Description**: Adds a new school to the database.
- **Request Payload**:

    ```json
    {
        "name": "Nutan High School",
        "address": "Kurduwadi, Solapur",
        "latitude": 50.7128,
        "longitude": -60.006
    }
    ```

- **Response**:

    ```json
    {
        "message": "School added successfully"
    }
    ```

### 2. List Schools

- **Endpoint**: `/api/listSchools`
- **Method**: `GET`
- **Description**: Retrieves a list of all schools, sorted by proximity to the user's location.
- **Query Parameters**:
  - `latitude`: User's latitude.
  - `longitude`: User's longitude.
- **Example Request**:

    ```url
   https://educase-assignment-j3kq.onrender.com/api/listSchools?latitude=40.712776&longitude=-74.005974
    ```

- **Response**:

    ```json
    [
    {
        "id": 1,
        "name": "Nutan High School",
        "address": "Kurduwadi, Solapur",
        "latitude": 50.7128,
        "longitude": -60.006
    },
    {
        "id": 2,
        "name": "Antar Bharti High School",
        "address": "Kurduwadi, Solapur",
        "latitude": 52.7128,
        "longitude": -63.006
    }
]
    ```
