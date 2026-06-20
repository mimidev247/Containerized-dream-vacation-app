# Containerized Dream Vacation App

This repository contains the complete Docker and Docker Compose environment configuration for local development, providing an end-to-end multi-container architecture using isolated services.

## Architecture Overview

The application infrastructure is orchestrated into three isolated services running on a custom bridge network:
* **Frontend:** A React application optimized using a multi-stage Docker build and served via an Nginx container.
* **Backend:** A Node.js runtime environment exposing the API service.
* **Database:** A PostgreSQL instance utilizing Docker named volumes for data persistence.

---

## Prerequisites

Before running the application, ensure you have the following installed on your system:
* Docker Engine
* Docker Compose Plugin

---

## Setup & Installation

### 1. Configure Environment Variables
Create a `.env` file in the root directory of the project to manage your database credentials securely:

```env
DB_USER=postgres
DB_PASSWORD=supersecurepassword123
DB_NAME=dream_vacation
