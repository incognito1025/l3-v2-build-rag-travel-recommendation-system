Here’s the cleaned-up version of the `frontend-setup.md` file, formatted for GitHub and with some improvements to meet the guidelines:

---

# Frontend Setup

## Installation

Ensure you have Node.js installed, then clone the repository and install dependencies:

```bash
# Clone the repository
git clone https://your-repository-url.git

# Create the frontend application with Vite
npm create @vitejs/app travel-recommendation-frontend --template react

# Navigate to the frontend directory
cd travel-recommendation-frontend

# Install dependencies
npm install
```

---

## Usage

To start the development server:

```bash
npm run dev
```

Then, open your browser and navigate to:

```
http://localhost:5180/
```

For production build:

```bash
npm run build
```

---

## Dependencies

Core dependencies:

```bash
# Core dependencies
npm install react react-dom react-router-dom redux react-redux axios dotenv
```

Development dependencies:

```bash
# Development dependencies
npm install --save-dev eslint @eslint/js @types/react @types/react-dom @vitejs/plugin-react vite
```

---

## Environment Setup

### Create a `.gitignore` file

```bash
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

### Create a `.env` file

Include the following environment variable in your `.env` file:

```bash
PORT=PORTNUMBER
```

---

### Add Scripts to `package.json`

Ensure the `scripts` section of `package.json` includes the following:

```json
"scripts": {
  "start": "node server.js",
  "dev": "nodemon server.js"
}
```

---

## Project Structure

Here is the directory and file layout of the project:

```
travel-recommendation-system-frontend/
│
├─── node_modules/
├─── public/
│ └─── favicon.ico
├─── src/
│ ├─── Components/
│ │ ├─── NavBar.jsx
│ │ ├─── RecommendationList.jsx
│ │ ├─── RecommendationCard.jsx
│ │ └─── PreferenceForm.jsx
│ │
│ ├─── Pages/
│ │ ├─── HomePage.jsx
│ │ ├─── RecommendationPage.jsx
│ │ └─── ErrorPage.jsx
│ │
│ ├─── assets/
│ │ └─── travel.webp
│ │
│ ├─── App.css
│ ├─── App.jsx
│ ├─── index.css
│ └─── main.jsx
│
├─── .gitignore
├─── .eslintrc.cjs
├─── README.md
├─── package-lock.json
├─── package.json
└─── vite.config.js
```

---

## Components Overview

### Components

- NavBar.jsx – Navigation bar
- RecommendationList.jsx – Displays recommended destinations
- RecommendationCard.jsx – Individual recommendation cards
- PreferenceForm.jsx – User input form for travel preferences

### Pages

- HomePage.jsx – Welcome and introduction
- RecommendationPage.jsx – Displays travel suggestions
- ErrorPage.jsx – Handles incorrect routes or errors

---

## Development Approach

This project follows a structured, tiered approach:

### Tier 1: Basic functionality
- User inputs travel preferences
- System provides basic recommendations

### Tier 2: Improved UX & Features
- Enhanced UI design
- Weighted recommendations

### Tier 3: Advanced features
- AI-powered insights
- Interactive user analytics

For further details, see `tier.md`.

---

## Backend and Database

- Backend API – Processes travel recommendations
- Database – PostgreSQL with pgvector for embeddings
- Backend Repository: [Link Here](#)

---

## Technologies

[![My Skills](https://skillicons.dev/icons?i=react,redux,js,html,css,vite,vercel)](https://skillicons.dev)
