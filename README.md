# airbnb-clone-project

## Overview
This is a scalable and production-ready **AirBnB clone** built to demonstrate full-stack development with a modern, asynchronous architecture. It focuses on delivering core functionality, like property listings, bookings, and user interactions, while showcasing background processing, flexible APIs, and development agility.

#### Project Goals
- Rebuild key Airbnb-like features: user registration, property listings, search and booking flows, and notifications.
- Build a clean, maintainable codebase that’s easy to test, extend, and deploy.
- Use automation to streamline development and promote a DevOps-oriented workflow.

#### Technology Stack
- **Django**
- **Django REST Framework** 
- **PostgreSQL**
- **GraphQL** 
- **Celery**
- **Redis** 
- **Docker**
- **CI/CD Pipelines** 
  


## Team Roles

| Role                      | Responsibilities |
|---------------------------|------------------|
| **Backend Developer**     | Implements API endpoints, defines database schemas, and handles business logic. |
| **Database Administrator** | Designs and optimizes database schemas, manages indexing and performance tuning. |
| **DevOps Engineer**       | Oversees deployment pipelines, monitoring, and ensures scalable backend infrastructure via CI/CD. |
| **QA Engineer**           | Tests backend functionality, validates quality standards, and reports defects. |

---

## Technology Stack

A high-level overview of the core technologies leveraged in this project:

- **Django**: A high-level Python web framework used to create a robust foundation for building RESTful APIs and core backend logic.
- **Django REST Framework**: Extends Django with powerful tools and abstractions for building and managing RESTful API endpoints.
- **PostgreSQL**: A reliable, production-grade relational database system used to store and manage structured data with strong integrity and performance.
- **GraphQL**: Provides flexible, efficient, and client-driven data querying capabilities, allowing consumers to request exactly what they need.
- **Celery**: A distributed task queue used to process asynchronous jobs such as sending notifications or processing payments, outside the main request lifecycle.
- **Redis**: Serves dual roles as a high-performance in-memory cache and as a message broker for Celery tasks, improving response times and background processing.
- **Docker**: Containerization tool that ensures a consistent and reproducible development and deployment environment across all stages of the project lifecycle.
- **CI/CD Pipelines**: Automated workflows that build, test, and deploy code changes, ensuring stability and speed in delivery.

---
## Database Design

This section outlines the key entities required for the AirBnB Clone project, important fields for each, and how they interrelate.

### Entities & Key Fields

#### **Users**
- `id` (PK)
- `username`
- `email`
- `password_hash`
- `created_at`

#### **Properties**
- `id` (PK)
- `host_id` (FK → Users.id)
- `title`
- `location`
- `price_per_night`

#### **Bookings**
- `id` (PK)
- `user_id` (FK → Users.id)
- `property_id` (FK → Properties.id)
- `start_date`
- `end_date`

#### **Payments**
- `id` (PK)
- `booking_id` (FK → Bookings.id)
- `amount`
- `payment_method`
- `payment_date`

#### **Reviews**
- `id` (PK)
- `user_id` (FK → Users.id)
- `property_id` (FK → Properties.id)
- `booking_id` (FK → Bookings.id)
- `rating`
- `comment`

---

### Relationships

- A **User** (as host) **can own many** **Properties**.
- A **User** (as guest) **can create many** **Bookings**.
- A **Booking** **belongs to one** **Property** and one **User**.
- Each **Booking** typically has one **Payment** associated.
- A **User** **can write many** **Reviews**, each linked to a **Property** and **Booking**.


---
## Feature Breakdown

Below are the core features of the project, each supporting a critical aspect of the user experience and system functionality.

### User Management  
Enable users, both guests and hosts, to register, log in (including third-party options like Google or social media), and manage profiles with photos and bios. This builds trust and makes the platform more secure and personal.  

### Property Management  
Hosts can create and manage listings by adding descriptions, high-quality photos, availability calendars, pricing, and amenities. This functionality is essential for showcasing rentals effectively.  


### Search & Booking System  
Guests can search for rentals using filters like location, price, and availability, and then request or instantly book a property. This ensures a seamless reservation experience from discovery to booking.  

### Secure Payments  
Integrate secure payment gateways such as PayPal, Stripe, credit/debit cards in order for guests to make payments safely and hosts receive payouts seamlessly. This functionality instills user confidence and supports smooth transactions.  


### Reviews & Ratings  
Guests can leave reviews and ratings for properties and hosts after their stays. This system fosters transparency, builds trust, and helps maintain quality in the marketplace.  

### Messaging System  
Built-in communication enables guests and hosts to chat before, during, and after stays, facilitating questions, clarifications, and rapport building. It enhances user experience and reduces friction.  
