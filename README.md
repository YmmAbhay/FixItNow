# 🛠️ FixItNow - Neighborhood Service & Repair Marketplace

## 📖 Project Overview

FixItNow is a full-stack neighborhood service platform designed to connect residents with nearby verified service professionals (electricians, plumbers, carpenters, cleaners, etc.).

This repository contains the progress of the application development from **Week 1 to Week 5**, encompassing the core authentication, service listing, location-based searching, and the complete booking transaction engine.

---

## 💻 Tech Stack

* **Frontend:** React.js, Tailwind CSS, React Router
* **Backend:** Spring Boot (Java), Spring Security
* **Database:** MySQL, Hibernate / Spring Data JPA
* **Authentication:** JWT (JSON Web Tokens) for stateless session management
* **External APIs:** Google Maps API, HTML5 Geolocation API

---

## 🚀 Development Progress (Weeks 1 - 5)

### 🚩 Milestone 1: Authentication & Basic Setup (Weeks 1 - 2)

* **Project Architecture:** Initialized the React frontend and Spring Boot backend repositories.
* **Database Design:** Created the initial MySQL schemas for `Users` with distinct roles (`CUSTOMER`, `PROVIDER`, `ADMIN`).
* **Secure Auth:** Implemented robust JWT-based login and registration flows to protect API endpoints.
* **Role-Based Routing:** Built secure React routes ensuring users are directed to their specific dashboards based on their role.
* **Provider Onboarding:** Developed a specialized registration form for providers to input their service categories, skills, and capture their exact location coordinates using the browser's Geolocation API.

### 🚩 Milestone 2: Service Listings & Search (Weeks 3 - 4)

* **Service Catalog:** Created the database structure for parent categories (e.g., Plumbing) and subcategories (e.g., Pipe Repair).
* **Provider Services Manager:** Built a CRUD interface for providers to list their specific offerings, setting custom prices and availability.
* **Customer Discovery:** Developed the main Customer Dashboard allowing users to browse services dynamically.
* **Map Integration:** Integrated Google Maps API to visually display nearby service providers based on the customer's radius.
* **Service Details:** Built the detail view for individual services, displaying the provider's information, aggregate ratings, and historical reviews.

### 🚩 Milestone 3 (Part 1): Core Booking Engine (Week 5)

* **Time Slot Selection:** Integrated a calendar and time-slot picker into the Service Detail page.
* **Transactional Payload:** Engineered a secure booking creation flow that maps the `customerId`, `providerId`, and `serviceId` together into the database.
* **Provider Request Dashboard:** Built a real-time queue where providers can view incoming jobs and their specific details.
* **Lifecycle State Machine:** Implemented the full job status flow (`PENDING` → `CONFIRMED` → `COMPLETED` or `CANCELLED`). Providers and Customers can update these statuses dynamically without page reloads.

---

## ⚙️ How to Run the Project Locally

### 1. Database Setup

1. Open MySQL Workbench.
2. Create a new schema named `fixitnow`.
3. Update your Spring Boot `application.properties` with your MySQL username and password.

### 2. Start the Backend (Spring Boot)

1. Navigate to the `backend` folder.
2. Run `mvn clean install` to install dependencies.
3. Run the application via your IDE or using `mvn spring-boot:run`. The API will start on `http://localhost:8080`.

### 3. Start the Frontend (React)

1. Navigate to the `frontend` folder.
2. Run `npm install` to install dependencies.
3. Add your Google Maps API key to your `.env` file (`REACT_APP_GOOGLE_MAPS_API_KEY=your_key_here`).
4. Run `npm start`. The app will open at `http://localhost:3000`.

---

## 🔜 Next Steps (Week 6)

Currently working towards the completion of Milestone 3, which focuses on user interaction:

* **Real-Time Chat:** Implementing WebSockets (Spring WebSocket + STOMP) to allow customers and providers to message each other directly within the app regarding job details.
* **Review & Rating System:** Enabling customers to leave a 1-5 star rating and feedback comment after a provider marks a job as `COMPLETED`.
