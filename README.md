# Working With Forever — Full-Stack E-Commerce Platform

A professional, responsive, and modular full-stack e-commerce web application designed for showcasing and selling wellness and personal care products. This platform implements secure token-based user onboarding, dynamic cart orchestration, real-time checkouts, previous purchase history tracking, career application pipelines, and automated customer assistance.

The core architecture, database schema configurations, and key technical highlights outlined below can also be cross-referenced in the comprehensive `RESUME_TECH_REPORT.md` file[cite: 1].

---

## 🚀 Key Features

* **Dual-Driver Storage**: Abstracted data layer capable of hot-swapping between **Supabase (Cloud PostgreSQL)** and a **local JSON database** (`db.json`) for seamless offline operation and rapid local development.
* **Secure Authentication**: Secure token-based onboarding and session management using JSON Web Tokens (JWT) and `bcryptjs` password hashing.
* **Dynamic Cart & Checkout**: Interactive, real-time client-side cart orchestration and calculation with payment confirmation and order tracking.
* **Admin Control Panel**: Real-time business metrics dashboard, user/order statistics reporting, dynamic inventory CRUD operations, order fulfillment status updates, and a career applicant review system.
* **Automated Support**: Integrated automated customer assistance handling FAQs and routine customer service requests.
* **Performance Optimized**: Chronologically indexed database queries (`created_at DESC`) and optimized lookup structures to maximize speed.

---

## 🛠️ Technology Stack & Architecture

### Frontend Layer
* **Templating**: Embedded JavaScript (EJS) for dynamic server-side page rendering.
* **Styling**: HTML5 & Vanilla CSS3 utilizing modern CSS custom properties (variables), Flexbox, and CSS Grid for fluid, device-agnostic layouts.
* **Client-Side Scripting**: Vanilla JavaScript for asynchronous API requests (`fetch`), slide-out drawer menus, interactive page loaders, cart manipulation, and session validation.

### Backend Layer
* **Runtime**: Node.js
* **Framework**: Express.js (Modular RESTful API design, custom middleware pipeline, and robust routing)[cite: 1, 2].
* **Security & Utility Middleware**:
  * `helmet` — Secure HTTP header enforcement[cite: 1, 2].
  * `cors` — Cross-Origin Resource Sharing configuration[cite: 1, 2].
  * `morgan` — Server-side HTTP request logging[cite: 1, 2].
  * Custom authentication middleware for role-based route protection (`customer` vs. `admin`)[cite: 1, 2].

### Database & Storage
* **Production**: **Supabase (Cloud PostgreSQL)** utilizing custom relational tables, complex database triggers, performance indexing, and Row-Level Security (RLS) policies[cite: 1, 2].
* **Development/Offline**: Local file-system JSON driver acting as a reliable, zero-config document store[cite: 1, 2].

---

## 📋 Directory Structure

```text
working-with-forever/
├── backend/
│   ├── src/
│   │   ├── config/         # Database drivers & configuration
│   │   ├── middleware/     # Auth, security, and logging middleware
│   │   ├── routes/         # REST API endpoints (auth, products, orders, careers)
│   │   ├── controllers/    # Request handlers & business logic
│   │   └── server.js       # Application entry point[cite: 1, 2]
├── public/                 # Static assets (images, CSS styles, client JS)
├── views/                  # EJS server-rendered templates (pages, partials)
├── db.json                 # Local fallback/offline JSON storage[cite: 1, 2]
├── FINAL_SUPABASE_SCHEMA.sql # Production database setup scripts[cite: 1, 2]
├── package.json            # Node.js dependencies & scripts
└── README.md               # Project documentation
