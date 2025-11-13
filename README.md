#### Update: 10-24-2025

# Check-In Service

A modern web application for managing child check-ins at educational facilities. Built with React and Node.js.

---

### Project Overview

The Check-In Service is designed to enhance child safety and security in educational facilities. In an era where child protection is paramount, this system provides a robust, digital solution to prevent unauthorized pick-ups and ensure children's safety from potential risks such as kidnapping or abduction.

### Key Safety Features
- Secure QR code-based verification system for authorized pick-ups
- Real-time notifications to guardians when their child is checked in/out
- Comprehensive tracking of all check-in/out activities

### Target Users
- Educational Facilities (Kindergartens, Schools, Academies) 
- Parents and Legal Guardians
- Facility Administrators and Staff
- Child Safety Organizations

---

## Features

### Authentication & User Management
- Multi-role user system (Admin, Director, Manager, Guardian)
- Social login support (Google, Kakao)
- Password recovery and account management

### Check-In System
- QR code-based check-in system
- Real-time check-in status updates
- Multiple camera support for QR scanning
- Instant notifications to guardians

### Location Management
- Multiple location support
- QR code generation for each location
- Location-specific check-in history

### Child Management
- Child registration and guardian assignment
- Check-in history tracking
- Email notifications for guardians
- PDF receipt generation for check-in/out records

### Real-time Features
- Socket.IO based real-time notifications
- Instant check-in/out status updates
- Live dashboard updates across user roles

---

## Tech Stack

### Frontend
| Category | Technologies |
|----------|-------------|
| Core | React 19 |
| Build Tool | Vite |
| Routing | React Router v6 |
| Network | Axios |
| UI/UX | React Icons, React Hot Toast |
| Forms | Formik, Yup |
| QR Scanning | HTML5-QRCode |
| Date Picker | React Datepicker |

### Backend
| Category | Technologies |
|----------|-------------|
| Runtime | Node.js 20.x LTS |
| Framework | Express.js 5.x |
| Database | MySQL 8.0 |
| ORM | Sequelize 6.x |
| Authentication | Passport.js, JWT |
| Security | bcryptjs, helmet, express-rate-limit |
| Session | express-session, express-mysql-session |
| Real-time | Socket.IO 4.x |
| Caching | node-cache |
| QR Code | QRCode |
| PDF Generation | pdf-lib, pdf-to-printer |
| Email | Nodemailer |
| Logging | Winston, winston-daily-rotate-file |
| Validation | express-validator |
| API Docs | Swagger (swagger-jsdoc, swagger-ui-express) |
| Testing | Jest, Supertest |
| Development | nodemon |

---

## Documentation

### API Documentation
- Development: http://localhost:5050/api-docs (Swagger UI)
- See `docs/API_DOCUMENTATION.md` for detailed API reference
- Available in English and Korean (API_DOCUMENTATION_KR.md)

### Additional Documentation
- **Database Schema**: `docs/DB_SCHEMA.md` (also available in Korean)
- **Deployment Guide**: `docs/DEPLOYMENT_GUIDE.md` - PM2 deployment with HTTPS
- **Deployment Guide v2**: `docs/DEPLOYMENT_GUIDE_ver2.md` - Comprehensive HTTPS deployment
- **Docker Deployment**: `DOCKER_DEPLOYMENT.md` - Container-based deployment
- **Operation Manual**: `docs/OPERATION_MANUAL.md` - System operations and maintenance
- **E2E Testing**: `docs/E2E.md` - End-to-end testing guide
- **Project Completion**: `docs/COMPLETION.md` - Project completion report

---

## Getting Started

### Prerequisites
- Node.js 20.x LTS or higher
- MySQL 8.0 or higher
- npm or yarn

### Installation

1. Clone the repository
```bash
git clone [repository-url]
```

2. Install backend dependencies
```bash
cd checkin_api
npm install
```

3. Install frontend dependencies
```bash
cd checkin_ui
npm install
```

4. Configure environment variables
- Create `.env` files in both frontend and backend directories
- Set up necessary environment variables based on `.env.example`

5. Start the development servers

Backend:
```bash
cd checkin_api
npm run dev
```

Frontend:
```bash
cd checkin_ui
npm run dev
```

---

## Testing

### Running Tests

Backend tests (Unit + Integration):
```bash
cd checkin_api
npm test
```

Run specific test suites:
```bash
# Unit tests only
npm test -- --testPathPattern=unit

# Integration tests only
npm test -- --testPathPattern=integration
```

---

## Deployment

### Option 1: Traditional Deployment (PM2)
See `docs/DEPLOYMENT_GUIDE.md` for detailed instructions on deploying with PM2, Nginx, and SSL/TLS configuration.

### Option 2: Docker Deployment
See `DOCKER_DEPLOYMENT.md` for containerized deployment using Docker and Docker Compose.

Key deployment features:
- HTTPS/SSL support with Let's Encrypt
- PM2 process management with cluster mode
- Nginx reverse proxy configuration
- Automated backups and log rotation
- System monitoring and health checks

---

## Project Structure

### Frontend Structure
```
checkin_ui/
├── src/
│   ├── assets/         # Static assets and styles
│   ├── components/     # Reusable components
│   ├── hooks/         # Custom React hooks
│   ├── pages/         # Page components
│   ├── services/      # API service layers
│   └── validations/   # Form validation schemas
```

### Backend Structure
```
checkin_api/
├── app/
│   ├── configs/       # Configuration files
│   ├── controllers/   # Request handlers
│   ├── middlewares/   # Custom middlewares
│   ├── models/        # Database models
│   ├── routes/        # API routes
│   ├── services/      # Business logic
│   └── validations/   # Input validation
├── migrations/        # Database migrations
└── seeders/          # Database seeders
```

---

## Security Features
- Session-based authentication with secure cookies
- OAuth 2.0 integration (Google, Kakao)
- Rate limiting for login attempts
- Secure password hashing with bcryptjs
- CORS protection with configurable origins
- Input validation and sanitization
- Helmet middleware for HTTP headers security
- Environment-based configuration management

---

## Logging and Monitoring
- Winston logger with daily log rotation
- Separate log files for errors and combined logs
- PM2 process monitoring
- Application performance tracking
- System resource monitoring

---

## Database Migrations and Seeding

### Running Migrations
```bash
cd checkin_api
npx sequelize-cli db:migrate
```

### Seeding Demo Data
Run each seed file in order:
```bash
npx sequelize-cli db:seed --seed 20250626220647-demo-location.js
npx sequelize-cli db:seed --seed 20250626220226-demo-user.js
npx sequelize-cli db:seed --seed 20250626220855-demo-child.js
npx sequelize-cli db:seed --seed 20250626221248-demo-userChild.js
npx sequelize-cli db:seed --seed 20250707132956-demo-history.js
```

Or seed all at once:
```bash
npx sequelize-cli db:seed:all
```

---

## Contributing

Please refer to the project documentation in the `docs/` folder for contribution guidelines and coding standards.

---

## License

Private - All rights reserved

---

## Support

For technical issues or questions:
- Check the documentation in the `docs/` folder
- Review API documentation at `/api-docs` endpoint
- Refer to the Operation Manual for system administration
