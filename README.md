# 📊 Sheet Insights: MERN-Stack Excel Analytics Platform

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)

**Sheet Insights** is a full-stack MERN application that transforms raw Excel spreadsheets into interactive, web-based dashboards. It serves as a lightweight Business Intelligence (BI) tool, allowing users to upload data and instantly receive automated visualizations and summary insights.

---

## 👥 Project Context & Team

This application was developed as the primary capstone project for the **3-month MERN Stack Internship at Zidio Development**. The objective was to build a complex, real-world application from scratch, demonstrating our ability to collaborate, manage a codebase, and deploy a full-stack product.

### Our Team
* **Rajneesh** – Lead Developer
* **Tanmay Upadhyay** – Lead Backend Developer
* **Logesh** – Head of UI/UX Design
* **Siddhartha Karumuri** – Project Contributor
* **Krish** – Team Member
* **Hemu** – Team Member

---

## 🎯 The Problem

In many business and academic settings, valuable data is locked away in `.xlsx` or `.csv` files. Analyzing this data typically requires manual effort in Excel or specialized, complex BI software. These methods can be slow, difficult to share, and inaccessible to non-technical users.

## ✨ The Solution

**Sheet Insights** provides a fast, accessible, and user-friendly web application to solve this. Any user can:
1.  **Upload** a raw data file.
2.  **Instantly View** a dashboard of automatically generated charts and key metrics.
3.  **Securely Manage** their data with a proper user account and authentication.

## 🌐 Live Demo & Screenshots

**Try the app live:** [**Click here to visit SightInsights**](https://sheetinsights.netlify.app/)

Screenshot of the live site:

| Home Page View | Login Page |
| :---: | :---: |
| <img width="1920" height="1080" alt="Screenshot (5)" src="https://github.com/user-attachments/assets/145005ba-a1e9-4d25-85fe-2db80960b5f9" /> | <img width="1920" height="1080" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/79d15698-4fbf-48d1-bb24-d0dac81edb58" />
| User Dashboard Data Analysis | Admin Dashboard Data Analysis |
| <img width="1920" height="1080" alt="Screenshot (7)" src="https://github.com/user-attachments/assets/7fffb025-f2b3-45c7-9f50-64aca70eb2fd" /> | <img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/66579e14-f921-4aff-96dd-80f8dc2a16aa" />
| SuperAdmin Dashboard Data Analysis | Team |
| <img width="1920" height="1080" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/71bf3a52-4b1c-43df-bc0b-5eb06cd6f12b" /> | <img width="1920" height="1080" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/03a299bb-8e8f-4437-b1f4-bad1e1e57a36" />



---

## 🏗️ Architecture Overview

This project is a **decoupled MERN-stack application**. The frontend and backend are separate, independent applications that communicate via a RESTful API.

* **Frontend (Client):** A React.js Single-Page Application (SPA) deployed on **Netlify**. It handles all user interface elements, state management, and data visualization.
* **Backend (Server):** A Node.js & Express.js RESTful API deployed on **Render**. It manages all business logic, database interactions, file processing, and user authentication.
* **Database:** A **MongoDB Atlas** cloud database stores all user information and processed data, accessed securely by the backend server.



This decoupled architecture makes the application scalable, easier to maintain, and allows the frontend and backend to be developed and deployed independently.

## ⚙️ Technical Data Flow (How it Works)

When a user uploads a file, the following process is triggered:

1.  **Client Request:** The **React** frontend sends the file (as `multipart/form-data`) to a secure API endpoint on the **Node.js/Express** server.
2.  **File Interception:** The **Multer** middleware on the server intercepts the incoming file, temporarily storing it in memory.
3.  **Data Parsing:** The **XLSX (SheetJS)** library reads the file buffer, parses the spreadsheet data, and converts it into a JSON object array.
4.  **Business Logic:** The server's controller logic processes this JSON data—performing calculations, aggregations, or summaries as required.
5.  **Database Storage:** **Mongoose** is used to validate and save the processed data into the **MongoDB Atlas** database, associating it with the authenticated user.
6.  **API Response:** The server sends a success response (or error) back to the client.
7.  **Data Visualization:** The React client, upon receiving success, makes a new `GET` request to another endpoint to fetch the processed data. This data is then passed to **Chart.js/Recharts** components to render the interactive dashboard.

## 💡 Key Features

* **Role-Based Access Control (RBAC):** Secure **JWT (JSON Web Token)** authentication with three distinct user roles:
    * **User:** Can upload, view, and manage their own data files.
    * **Admin:** Can manage users and system settings.
    * **Superadmin:** Has full system oversight.
* **Dynamic Data Dashboard:** Instantly generates a suite of interactive charts and summary cards upon file upload, allowing for immediate data exploration.
* **Flexible File Ingestion:** Supports both `.xlsx` and `.csv` formats using a robust backend parsing engine.
* **Fully Responsive UI:** A clean, modern, and mobile-first interface built with **Tailwind CSS**.

## 🚀 Tech Stack

| Area | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend** | React.js, Tailwind CSS | A responsive SPA for all user interactions. |
| **Backend** | Node.js, Express.js | A RESTful API server for business logic and data. |
| **Database** | MongoDB Atlas, Mongoose | NoSQL database for storing user accounts and data. |
| **Authentication** | JSON Web Tokens (JWT) | For stateless, secure user session management. |
| **File Handling** | Multer, XLSX (SheetJS) | To handle file uploads and parse spreadsheet data. |
| **Data Visualization** | Chart.js, Recharts | Client-side libraries for interactive charts. |
| **Deployment** | Netlify (Frontend), Render (Backend) | CI/CD pipelines for high availability and global CDN. |

---

## 📈 Key Learnings & Challenges

This internship project was a simulation of a professional development environment and provided several key takeaways:

* **Handling File Uploads:** Implementing a robust file-handling pipeline (from client to server to database) was a major challenge. We learned to securely manage file streams, parse binary data in Node.js, and handle potential memory issues.
* **State Management in React:** We learned the importance of separating global state (like user auth) from local component state (like form inputs) to build a performant and maintainable frontend.
* **Team Collaboration & Git Workflow:** As a team, we enforced a strict Git workflow (using feature branches, pull requests, and code reviews). This was critical for managing a decoupled codebase and preventing conflicts.
* **Securing a Decoupled API:** We learned that a public frontend and a public API require separate security measures. We implemented CORS, JWT authentication, and role-based middleware on the backend to ensure data could only be accessed by authenticated and authorized users.