## Backend Setup for Travel Recommendation API

### Step 1: Environment Setup

1. Install Node.js and npm:
   - Download and install from [nodejs.org](https://nodejs.org), if not already installed.

2. Initialize a New Node.js Project:
   ```bash
   mkdir travel-recommendation-backend
   cd travel-recommendation-backend
   npm init -y
   ```

### Step 2: Install Dependencies

1. Install Essential Packages:
   ```bash
   npm install express pg cors dotenv axios
   ```

   - express: A web application framework for Node.js.
   - pg: Library for interacting with PostgreSQL.
   - cors: Middleware for handling Cross-Origin Resource Sharing.
   - dotenv: For managing environment variables.
   - axios: For making HTTP requests, useful for API calls.

2. Install Development Dependencies:
   ```bash
   npm install --save-dev nodemon
   ```

   - nodemon: Automatically restarts your Node.js application when it detects file changes.

### Step 3: Setup Environment Variables

1. Create a `.gitignore` File:
   ```gitignore
   # Node modules
   node_modules/

   # Logs
   *.log

   # Environment variables
   .env

   # Optional npm cache
   .npm

   # Debug
   npm-debug.log*

   # Editor folders
   .idea/
   .vscode/

   # System files
   .DS_Store
   ```

2. Create a `.env` File:
   ```env
   PG_USER=yourpostgresusername
   PG_HOST=localhost
   PG_DATABASE=travel_recommendation
   PG_PASSWORD=yourpostgrespassword
   PG_PORT=5432
   OPENAI_API_KEY=your_openai_api_key
   ```

### Step 4: Validate and Run

1. Add Scripts to `package.json`:
   Add these scripts to the `"scripts"` section:
   ```json
   "scripts": {
     "start": "node server.js",
     "dev": "nodemon server.js"
   }
   ```

2. Run the Development Server:
   ```bash
   npm run dev
   ```

### Step 5: Project Structure

#### Directory and File Layout:

```plaintext
travel-recommendation-backend/
├── config/
│   ├── database.js
│   └── config.js
├── controllers/
│   ├── authController.js
│   ├── userController.js
│   └── recommendationController.js
├── models/
│   ├── userModel.js
│   └── recommendationModel.js
├── routes/
│   ├── authRoutes.js
│   ├── userRoutes.js
│   └── recommendationRoutes.js
├── middlewares/
│   ├── authMiddleware.js
│   └── errorHandler.js
├── services/
│   ├── recommendationService.js
│   └── authService.js
├── utils/
│   ├── helperFunctions.js
│   └── logger.js
├── .env
├── .gitignore
├── package.json
├── app.js
└── server.js
```

#### Description of Each Component:

- config/: Contains configuration files for database connections and application-specific settings.
- controllers/: Handles incoming requests, containing logic for authentication, user management, and recommendations.
- models/: Defines data models and schemas, interacting directly with the database.
- routes/: Maps HTTP requests to controller functions.
- middlewares/: Functions that handle requests prior to reaching endpoint handlers.
- services/: Core business logic, abstracted from controllers for reuse and clarity.
- utils/: Utility functions and helpers for common tasks like logging or data formatting.

### Step 6: Configure the Server

1. Create a Basic Express Server (`server.js`):
   ```javascript
   require('dotenv').config();
   const express = require('express');
   const cors = require('cors');
   const { Pool } = require('pg');

   const app = express();
   app.use(cors());
   app.use(express.json());

   const pool = new Pool({
     user: process.env.PG_USER,
     host: process.env.PG_HOST,
     database: process.env.PG_DATABASE,
     password: process.env.PG_PASSWORD,
     port: process.env.PG_PORT,
   });

   app.listen(3000, () => {
     console.log('Server is running on port 3000');
   });
   ```

2. Main Configuration in `app.js`:
   ```javascript
   const express = require('express');
   const app = express();

   // Add middleware, routes, and other configurations
   ```

3. Run Server in Development Mode:
   ```bash
   npx nodemon server.js
   ```

### Step 7: Integrate OpenAI API

1. Example API Call:
   ```javascript
   const axios = require('axios');

   async function getEmbedding(text) {
     try {
       const response = await axios.post('https://api.openai.com/v1/embeddings', {
         headers: {
           'Authorization': `Bearer ${process.env.OPENAI_API_KEY}`,
           'Content-Type': 'application/json',
         },
         data: {
           model: 'text-embedding-ada-002',
           input: text,
         },
       });
       return response.data.data;
     } catch (error) {
       console.error('Error fetching embedding from OpenAI:', error);
     }
   }
   ```

### Step 8: Set Up PostgreSQL with pgvector

1. Install PostgreSQL:
   - Follow installation instructions on the [PostgreSQL website](https://www.postgresql.org/download/).

2. Ensure `pgvector` is Installed:
   - You can install the `pgvector` extension if not already available.

3. Create Database and Table:
   ```sql
   CREATE DATABASE travel_recommendation;
   \c travel_recommendation;

   CREATE EXTENSION IF NOT EXISTS vector;

   CREATE TABLE profiles (
     id SERIAL PRIMARY KEY,
     preferences VECTOR(300),
     user_data JSONB
   );
   ```
