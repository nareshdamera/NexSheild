NEXSHEILD: Proactive and Personalized Security Alerting Platform

NEXSHEILD is a full-stack web application designed to help individuals and organizations stay ahead of security threats by providing highly targeted, real-time vulnerability alerts. Instead of wading through endless CVE lists, users are only notified when a new threat is relevant to the organizations or keywords they actively track.

🚀 Project Overview

The application is built on a modern MERN-like stack (MongoDB, Express, React, Node.js) and features an intelligent, automated data pipeline that handles monitoring, enrichment, and personalized alerting.

✨ Key Features

1. Automated Data Pipeline (Backend)

The core business logic runs on a daily schedule (via a Cron job) to ensure timely alerts:

Web Scraping (scraper.cjs): Scrapes the latest CVEs from the National Vulnerability Database (NVD) using Cheerio.

LLM Enrichment: New vulnerability data is passed to an external HuggingFace Large Language Model (LLM) to accurately identify the affected Company/Vendor Name and generate a concise summary.

Targeted Alerting (mail.cjs): Matches enriched vulnerabilities to registered users based on their custom keywords. Eligible users receive a direct email alert via Nodemailer.

2. User Authentication and Profile Management

Secure Authentication: User registration and login are handled with strong security practices, including password hashing via bcrypt and session management using JSON Web Tokens (JWT).

Personalized Tracking: The user profile (SettingsSection) allows users to manage their list of tracking keywords. This list is the foundation for determining which alerts they receive.

3. Frontend Experience (React)

The frontend is a dark-themed, responsive Single Page Application (SPA) built with React and styled with Tailwind CSS and Framer Motion for smooth animations.

Route

Purpose

Key Components

/

Marketing Landing Page

HeroSection, About, Testimonials

/login, /register

User Authentication

Login.jsx, Register.jsx

/Dashboard

Vulnerability Feed

VulerabilityList.jsx (searchable, paginated view of all CVEs)

/profile

User Settings

ProfilePage.jsx, SettingsSection.jsx (Manage account details and keywords)

⚙️ Technology Stack

Category

Technology

Purpose

Frontend

React, Tailwind CSS, Framer Motion, React Router

User Interface and Navigation

Backend

Node.js, Express, node-cron

API, Routing, and Job Scheduling

Database

MongoDB (Mongoose)

Data persistence for Users and Vulnerabilities

Utilities

Cheerio, Axios, Nodemailer, bcrypt, JWT

Web Scraping, HTTP Requests, Emailing, Security

Intelligence

HuggingFace LLM (via Inference Client)

Automated Data Enrichment

📦 Project Structure

The project follows a standard structure for full-stack development:

├── config/                  # Server configuration (e.g., generateToken)
├── controllers/             # Server business logic (userController, scraperController)
├── middleware/              # Authentication logic (authMiddleware)
├── models/                  # Mongoose schemas (userModel, vulnerabilityModel)
├── routes/                  # API endpoint definitions (userRoutes, scraperRoutes)
├── services/                # External services (mail.cjs)
├── src/                     # React Frontend source code
│   └── components/          # React components
│       └── ...              # (Login, Dashboard, Navbar, SettingsSection, etc.)
└── index.js                 # Server entry point, DB connection, Cron job setup
