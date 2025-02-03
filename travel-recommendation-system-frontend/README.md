# Travel Recommendation System Frontend

## Description

This is the frontend for the RAG-based Travel Recommendation System, providing personalized travel suggestions based on user preferences. It leverages data from the Mountains vs. Beaches Preference Dataset and integrates with an AI-powered backend.

- Frontend Framework: React with Vite
- State Management: Redux
- Routing: React Router DOM
- Backend Integration: Axios for API communication
- Live App: [Coming Soon]
- Backend Repository: [Link Here](#)

---

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Technologies](#technologies)
- [Project Structure](#project-structure)
- [Components Overview](#components-overview)
- [Development Approach](#development-approach)

---

## Features

✅ Interactive form for user preferences input  
✅ AI-driven personalized travel recommendations  
✅ Dynamic results display with smooth UI/UX  
✅ Responsive design for mobile and desktop  
✅ Fast development with Vite

---

## Installation

Ensure you have Node.js installed, then clone the repository and install dependencies:

```sh
# Clone the repository
git clone https://your-repository-url.git
cd travel-recommendation-system-frontend

# Install dependencies
npm install
```

---

## Usage

To start the development server:

```sh
npm run dev
```

Then open your browser and navigate to:

```
http://localhost:5180/
```

For production build:

```sh
npm run build
```

## Dependencies

To install necessary dependencies:

```sh
# Core dependencies
npm install react react-dom react-router-dom redux react-redux axios dotenv

# Development dependencies
npm install --save-dev eslint @eslint/js @types/react @types/react-dom @vitejs/plugin-react vite
---

## Technologies

[![My Skills](https://skillicons.dev/icons?i=react,redux,js,html,css,vite,vercel)](https://skillicons.dev)

---

## Project Structure

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

### Components/
- NavBar.jsx – Navigation bar
- RecommendationList.jsx – Displays recommended destinations
- RecommendationCard.jsx – Individual recommendation cards
- PreferenceForm.jsx – User input form

### Pages/
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
### 🚀 Ready to explore your next adventure? Start your journey now!

```
