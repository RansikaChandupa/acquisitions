# Production Ready API

A production-ready RESTful API built with Node.js and Express, implementing secure user authentication and role-based access control.

## 🚀 Features

- **JWT Authentication** - Token-based authentication with secure HTTP-only cookies
- **Role-Based Authorization** - Admin and user roles with permission checks
- **Password Security** - Bcrypt hashing with salt rounds
- **Input Validation** - Zod schema validation for all user inputs
- **Database ORM** - Drizzle ORM with PostgreSQL (Neon serverless)
- **Structured Logging** - Winston logger for application monitoring
- **Security Middleware** - Helmet, CORS, and Arcjet protection
- **Error Handling** - Consistent error responses with proper HTTP status codes
- **Code Quality** - ESLint and Prettier configuration
- **Hot Reload** - Development mode with auto-restart
- **Docker Support** - Containerized deployment scripts
- **Clean Architecture** - Layered structure with separation of concerns

## 📋 Prerequisites

- Node.js (v18 or higher)
- PostgreSQL database or Neon serverless account
- Docker and Docker Compose (optional)

## 🛠️ Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/RansikaChandupa/Production-Ready-API-Project
   cd acquisitions
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Environment Configuration**

   Create environment files based on your deployment:

   **For Development (`.env.development`):**

   ```env
   # Server Configuration
   PORT=3000
   NODE_ENV=development
   LOG_LEVEL=debug

   # Database Configuration
   DATABASE_URL=your_postgresql_connection_string
   DATABASE_NAME=your_database_name

   # Neon Configuration
   NEON_API_KEY=your_neon_api_key
   NEON_PROJECT_ID=your_project_id
   PARENT_BRANCH_ID=your_branch_id
   DELETE_BRANCH=true

   # JWT Configuration
   JWT_SECRET=your_jwt_secret_key

   # Arcjet
   ARCJET_KEY=your_arcjet_key
   ```

   **For Production (`.env.production`):**

   ```env
   # Server Configuration
   PORT=3000
   NODE_ENV=production
   LOG_LEVEL=info

   # Database Configuration
   DATABASE_URL=your_postgresql_connection_string
   DATABASE_NAME=your_database_name

   # Neon Configuration
   NEON_API_KEY=your_neon_api_key
   NEON_PROJECT_ID=your_project_id
   PARENT_BRANCH_ID=your_branch_id
   DELETE_BRANCH=false

   # JWT Configuration
   JWT_SECRET=your_jwt_secret_key

   # Arcjet
   ARCJET_KEY=your_arcjet_key

   # Security Configuration
   CORS_ORIGIN=https://yourdomain.com
   ```

4. **Database Setup**

   ```bash
   # Generate migration files
   npm run db:generate

   # Run migrations
   npm run db:migrate

   # (Optional) Open Drizzle Studio to manage database
   npm run db:studio
   ```

## 🚦 Running the Application

### Development Mode

```bash
# Run with auto-reload
npm run dev

# Run with Docker
npm run dev:docker
```

### Production Mode

```bash
# Standard start
npm start

# Docker production deployment
npm run prod:docker
```

## 📝 Available Scripts

| Script                 | Description                              |
| ---------------------- | ---------------------------------------- |
| `npm run dev`          | Start development server with hot reload |
| `npm start`            | Start production server                  |
| `npm run lint`         | Check code for linting errors            |
| `npm run lint:fix`     | Fix linting errors automatically         |
| `npm run format`       | Format code with Prettier                |
| `npm run format:check` | Check code formatting                    |
| `npm run db:generate`  | Generate database migration files        |
| `npm run db:migrate`   | Run database migrations                  |
| `npm run db:studio`    | Open Drizzle Studio GUI                  |
| `npm run dev:docker`   | Run development environment in Docker    |
| `npm run prod:docker`  | Run production environment in Docker     |
| `npm test`             | Run test suite                           |

## 🐳 Docker Deployment

```bash
# Development
docker-compose up

# Production
docker-compose -f docker-compose.prod.yml up -d
```
