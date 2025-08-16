# Home Swap Platform API

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![.NET Version](https://img.shields.io/badge/.NET-8.0-blueviolet)

A modern, robust platform for users to list and exchange their homes. Built with .NET and Clean Architecture, this project demonstrates best practices in software design, including CQRS, multi-database integration, and secure authentication.

---

## ✨ Features

### For Users
* **Secure Authentication:** Register and log in with a local account or via Google. Uses JWT with refresh tokens for secure sessions.
* **Home Management:** Easily create, update, and manage your home listings.
* **Photo Uploads:** Add multiple high-quality images to showcase your property.
* **Advanced Filtering:** Browse available homes with powerful server-side filtering by type, size, number of rooms, and garage availability.
* **Exchange System:** Send and receive exchange requests, including an optional surcharge or demand for payment.
* **Real-time Updates:** A seamless process for accepting requests and finalizing a swap.

### For Administrators
* **Comprehensive Dashboard:** View and manage all users, home listings, and completed exchanges.
* **Powerful Moderation:** Block users or specific home listings that violate platform rules.
* **Time-Locked Unblocking:** Unblock users or listings only within a 21-day window, ensuring fair and final moderation.
* **Blacklist Security:** A custom middleware automatically blocks access for blacklisted users, enhancing platform security.

---

## 🏗️ Technology & Architecture

This project is built using a modern, scalable technology stack and adheres to the principles of **Clean Architecture**.

* **Framework:** .NET 8
* **Architecture:** Clean Architecture
    * **Domain:** Contains core business logic and entities.
    * **Application:** Implements business logic, CQRS handlers, and interfaces.
    * **Infrastructure:** Handles data access, external services, and database integrations.
    * **Presentation (API):** Exposes the application via a RESTful API.
* **Key Patterns:**
    * **CQRS (Command Query Responsibility Segregation)** with `MediatR`
    * **Repository & Unit of Work** for data abstraction
    * **Dependency Injection** throughout the application
* **Databases:**
    * **Relational (PostgreSQL / SQL Server):** Manages all core data (Users, Homes, Exchanges).
    * **NoSQL Document (MongoDB):** Used for storing user activity logs or reviews.
    * **NoSQL Graph (Neo4j):** Powers a recommendation engine or maps user connections.

---

## 🚀 Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

* [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
* [Docker Desktop](https://www.docker.com/products/docker-desktop) (for running databases)
* A code editor like [Visual Studio Code](https://code.visualstudio.com/) or [Visual Studio 2022](https://visualstudio.microsoft.com/)

### Installation & Setup

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your-username/home-swap-platform.git](https://github.com/your-username/home-swap-platform.git)
    cd home-swap-platform
    ```

2.  **Configure Environment Variables:**
    * Rename the `appsettings.Development.json.example` file in the `Api` project to `appsettings.Development.json`.
    * Update the file with your database connection strings, JWT secret key, and Google Auth credentials.

3.  **Run Databases with Docker:**
    * A `docker-compose.yml` file is included to easily spin up the required databases.
    ```sh
    docker-compose up -d
    ```

4.  **Apply Database Migrations:**
    * Navigate to the `Api` project directory and run the Entity Framework Core migrations to set up the relational database schema.
    ```sh
    cd src/Api
    dotnet ef database update
    ```

5.  **Run the Application:**
    * You can now run the API project.
    ```sh
    dotnet run
    ```
    The application will be available at `https://localhost:5001`.

---

## 📚 API Documentation

The API is fully documented using **Swagger (OpenAPI)**. Once the application is running, you can access the interactive documentation and test the endpoints by navigating to:

**http://localhost:5000/swagger**

---

## 🤝 Contributing

Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.
