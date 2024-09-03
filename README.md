


# MERN Stack CRUD Application

This project is a MERN (MongoDB, Express, React, Node.js) stack CRUD application, orchestrated using Docker Compose. It includes three services: a MongoDB database, a backend API server built with Node.js, and a frontend React application.

## Prerequisites

Before running this project, ensure you have the following installed:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)

## Getting Started




### 1. Clone the Repository

```bash
git clone https://github.com/your-username/mern_stack_crud.git
cd mern_stack_crud
```

### 2. Set Up Environment Variables

Navigate to the `backend` directory and create a `.env` file to configure your backend service. Add the following environment variables:

```bash
cd backend
echo "PORT=8000" >> .env
echo "DB_URL=mongodb://mongo:27017/crud" >> .env
```

This configuration will:

- Set the backend server to run on port `8000`.
- Set the MongoDB connection URL to `mongodb://mongo:27017/crud`, where `mongo` refers to the MongoDB container defined in your `docker-compose.yaml` file.

### 3. Build and Run the Containers

To start all the services defined in the `docker-compose.yaml` file in detached mode, use the following command:

```bash
docker-compose up --build -d
```

This command will:

- Pull the latest MongoDB image and run it on port `27017`.
- Build and run the backend service on port `8000`.
- Build and run the frontend service on port `3000`.

### 4. Accessing the Application

Once the containers are up and running, you can access the application components as follows:

- **Frontend (React application)**: Open your web browser and go to [http://localhost:3000](http://localhost:3000).
- **Backend (Node.js API)**: The API server is accessible at [http://localhost:8000](http://localhost:8000).
- **MongoDB**: The MongoDB server is running on [localhost:27017](http://localhost:27017). You can connect to it using a MongoDB client (like [MongoDB Compass](https://www.mongodb.com/products/compass)).

### 5. Stopping the Containers

To stop and remove the running containers, networks, and volumes, run:

```bash
docker-compose down
```

This command will clean up all the resources created by Docker Compose.

## Project Structure

- `backend/`: Contains the Node.js API server code.
- `client/`: Contains the React frontend code.
- `docker-compose.yaml`: The Docker Compose configuration file.
