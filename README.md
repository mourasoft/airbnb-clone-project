# Airbnb Clone Project

<details>
<summary>ProDev Backend</summary>

## About the Project

The Airbnb Clone Project is a comprehensive, real-world application designed to simulate the development of a robust booking platform like Airbnb. It involves a deep dive into full-stack development, focusing on backend systems, database design, API development, and application security. Learners will build a scalable web application while collaborating in team workflows and applying industry best practices.

## Learning Objectives

- **GitHub Collaboration**  
  Master branching, pull requests, code reviews, and collaborative workflows.
- **Backend & Database Design**  
  Deepen understanding of RESTful API design, ORM modeling, and relational schemas.
- **API Security**  
  Implement authentication, authorization, rate-limiting, and input validation.
- **CI/CD Pipelines**  
  Design automated testing, build, and deployment workflows.
- **Documentation & Planning**  
  Strengthen project documentation, architectural diagrams, and task breakdowns.
- **Tech Integration**  
  Integrate Django, GraphQL, MySQL, Docker, and CI/CD tools in a unified ecosystem.

## Requirements

- GitHub account
- Familiarity with Markdown for README authoring
- Prior experience with Django (or similar backend framework)
- Basic knowledge of MySQL (or another relational database)
- Understanding of software development lifecycle, security, and CI/CD
- Comfort with Docker and a CI/CD platform (e.g., GitHub Actions)

## Key Highlights

- **Repository Management**  
  Initialize & structure a public GitHub repo with clear directories and README.
- **Team Roles**  
  Define responsibilities: backend, frontend, database, DevOps, QA, design, security.
- **Tech Stack Breakdown**  
  Document each technology’s role: Django for APIs, MySQL for data persistence, GraphQL for query flexibility.
- **Database Modeling**  
  Design entities, attributes, and relationships reflecting real-world booking logic.
- **Feature-Driven Development**  
  Outline core features with user flows and business logic impact.
- **Security Best Practices**  
  Apply OWASP principles: JWT auth, RBAC, CORS, CSRF protection, HTTPS enforcement.
- **Automated Deployments**  
  Set up Dockerized services and GitHub Actions to test, build, and deploy to AWS ECS.

---

## Team Roles

- **Backend Developer**  
  Designs and implements REST/GraphQL APIs using Django; writes business logic & unit tests.
- **Frontend Developer**  
  Builds responsive UI components; integrates with backend endpoints and handles state management.
- **Database Administrator**  
  Models relational schema in MySQL; optimizes queries, manages migrations, and ensures backups.
- **DevOps Engineer**  
  Containerizes services with Docker; configures CI/CD pipelines and deploys to AWS ECS.
- **QA Engineer**  
  Writes integration and end-to-end tests; ensures code quality with automated test suites.
- **UX/UI Designer**  
  Crafts wireframes and mockups; ensures usability and accessibility across devices.
- **Project Manager**  
  Coordinates tasks, tracks progress, and facilitates communication among team members.
- **Security Engineer**  
  Reviews code for vulnerabilities; implements security measures (auth, rate limits, input validation).

## Technology Stack

- **Django**  
  High-level Python web framework for rapid API development.
- **GraphQL (Graphene-Django)**  
  Flexible query language to fetch exactly the data clients need.
- **MySQL**  
  Relational database for storing users, listings, bookings, and payments.
- **Docker**  
  Containerization platform to ensure consistent environments.
- **GitHub Actions**  
  Automates linting, testing, building, and deployment workflows.
- **AWS ECS**  
  Managed container orchestration for scalable deployments.

## Database Design

| Entity         | Key Fields                                                              | Relationships                                                                    |
| -------------- | ----------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Users**      | `id`, `name`, `email`, `password_hash`, `role`                          | A user can own many Properties; can make many Bookings                           |
| **Properties** | `id`, `owner_id`, `title`, `description`, `location`, `price_per_night` | Each Property belongs to one User; has many Bookings & Reviews                   |
| **Bookings**   | `id`, `user_id`, `property_id`, `start_date`, `end_date`, `total_price` | A Booking belongs to one User and one Property; one-to-one with Payment & Review |
| **Reviews**    | `id`, `booking_id`, `rating`, `comment`, `created_at`                   | Each Review is linked to one Booking                                             |
| **Payments**   | `id`, `booking_id`, `amount`, `status`, `processed_at`                  | Each Payment corresponds to one Booking                                          |

## Feature Breakdown

- **User Management**  
  Registration, login/logout, profile editing, and role-based access control.
- **Property Listings**  
  Hosts can create, update, view, and delete property entries with images & amenities.
- **Search & Filtering**  
  Guests can search by location, dates, price range, and apply multiple filters.
- **Booking System**  
  Select dates, calculate pricing, confirm bookings, and view booking history.
- **Reviews & Ratings**  
  Post-stay feedback system with star ratings and comments.
- **Payment Processing**  
  Secure transactions via Stripe integration; handle payment confirmations and refunds.
- **Admin Dashboard**  
  Overview of users, listings, bookings, and system health metrics.
- **Notifications**  
  Automated email alerts for booking confirmations, reminders, and cancellations.

## API Security

- **Authentication**  
  JSON Web Tokens (JWT) for stateless, secure user sessions.
- **Authorization**  
  Role-Based Access Control (RBAC) to restrict endpoints by user role.
- **Rate Limiting**  
  Throttle requests per IP/user to mitigate abuse and DDoS risks.
- **Input Validation & Sanitization**  
  Enforce strict schemas to prevent SQL injection and XSS.
- **HTTPS Enforcement**  
  SSL/TLS for all API traffic to protect data in transit.
- **CORS & CSRF Protection**  
  Configure allowed origins and use CSRF tokens for state-changing requests.

## CI/CD Pipeline

1. **Lint & Test**
   - **GitHub Actions** runs linters (flake8, ESLint) and unit/integration tests on every PR.
2. **Build & Publish**
   - Build Docker images for backend and push to AWS ECR.
3. **Deploy**
   - Trigger Rolling Deployments on AWS ECS clusters.
4. **Infrastructure as Code**
   - Use Terraform to provision and manage AWS resources (VPC, ECS, RDS).
5. **Monitoring & Alerts**
   - Integrate CloudWatch alarms and Slack notifications for deployment status.

 </details>

<details>
<summary>ProDev Frontend</summary>

## UI/UX Design Planning

### Design Goals

- **Intuitive Navigation:** Allow users to find and filter properties with minimal effort.
- **Responsive Layout:** Ensure usability across desktop, tablet, and mobile.
- **Visual Consistency:** Maintain a cohesive look & feel aligned with Airbnb’s brand identity.

### Key Features

- Search bar with location, date, and guest filters
- Image carousel for property previews
- Clear “Book Now” call-to-action

### Primary Pages

| Page                      | Description                                                                                  |
| ------------------------- | -------------------------------------------------------------------------------------------- |
| **Property Listing View** | Grid of property cards with thumbnail, title, price/night, and rating.                       |
| **Listing Detailed View** | Full details: image gallery, description, amenities, host info, reviews, and booking widget. |
| **Simple Checkout View**  | Review dates, pricing breakdown, payment form, and confirmation button.                      |

**Why User-Friendly Design Matters:**  
Reducing cognitive load and making actions predictable increases trust, lowers abandonment rates, and drives bookings.

---

## UI/UX Design Planning

### Figma Style Properties

- **Color Styles:**
  - Primary: `#FF5A5F`
  - Secondary: `#484848`
  - Accent: `#00A699`
  - Background: `#FFFFFF`
  - Text: `#333333`
- **Typography:**
  - **Font Family:** Inter, sans-serif
  - **Weights:** 400 (Regular), 600 (Semi-Bold), 700 (Bold)
  - **Sizes:** 14px (Body), 16px (Subheading), 24px (Heading), 32px (Title)

**Importance of Identifying Design Properties:**  
Documenting colors and typography ensures consistency between mockups and code, speeds up hand-offs, and preserves brand integrity.

---

## Project Roles and Responsibilities

| Role                    | Key Responsibilities                                                                          |
| ----------------------- | --------------------------------------------------------------------------------------------- |
| **Project Manager**     | Plan sprints, track progress, communicate with stakeholders                                   |
| **Product Owner**       | Define user stories, prioritize backlog, clarify requirements                                 |
| **Scrum Master**        | Facilitate ceremonies, remove blockers, coach team on Agile practices                         |
| **Frontend Developers** | Build React components, integrate with APIs, implement responsive design                      |
| **Backend Developers**  | Design and implement Django/GraphQL APIs, enforce business logic, write unit tests            |
| **Designers (UX/UI)**   | Create wireframes and prototypes in Figma, maintain style guide (colors, typography, spacing) |
| **QA/Testers**          | Develop and execute test plans, report bugs, verify fixes                                     |
| **DevOps Engineers**    | Configure Docker, CI/CD pipelines, deploy to AWS ECS, monitor system health                   |

---

## UI Component Patterns

- **Navbar**  
  Responsive top bar with logo, search input, navigation links, and user menu.
- **Property Card**  
  Thumbnail, title, price, rating; click-through to detailed view.
- **Footer**  
  Site links (About, Help, Terms), social icons, copyright.

<d/etails>
