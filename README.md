# mini_orders
Mini Orders API

A small, production-like REST API for managing users, products, and orders with authentication, RBAC, validation, PostgreSQL persistence, and automated tests.
 Tech Stack

Backend: Node.js 18+, TypeScript, NestJS

Database: PostgreSQL + Prisma ORM

Auth: JWT (Access + Refresh)

Validation: class-validator

Testing: Jest + Supertest

Tooling: ESLint, Prettier, Husky, dotenv

CI/CD: GitHub Actions

 Features

User registration/login with hashed passwords

Role-based access control (admin / customer)

Products CRUD (admin-only mutations) with pagination & search

Orders with stock validation, total calculation, and status updates

Secure error handling & validation

Prisma migrations & seed script

Dockerized setup with PostgreSQL

 Folder Structure
src/
  auth/       # Auth & JWT logic
  users/      # User service
  products/   # Product CRUD
  orders/     # Order logic
  common/     # Guards, interceptors, pipes
  prisma/     # Prisma service
test/         # Jest + Supertest tests
prisma/       # schema & migrations

 Setup
# Clone repo
git clone https://github.com/yourname/mini-orders-api.git
cd mini-orders-api

# Install deps
npm install

# Setup env
cp .env.example .env

# Run DB with Docker
docker-compose up -d

# Migrate & seed
npm run migrate
npm run seed

# Run app
npm run start:dev

Testing
npm run test
 Environment Variables (.env.example)
DATABASE_URL=postgresql://user:pass@localhost:5432/ordersdb
JWT_ACCESS_SECRET=youraccesssecret
JWT_REFRESH_SECRET=yourrefreshsecret
ACCESS_TOKEN_EXP=15m
REFRESH_TOKEN_EXP=7d
PORT=3000
