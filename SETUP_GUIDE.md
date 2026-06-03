# National FPO Digital Market Linkage Platform - Setup Guide

## 🚀 Quick Start

### Prerequisites
- Node.js 20+
- PostgreSQL 13+
- Docker & Docker Compose (optional)

### Local Setup

```bash
# Clone and install
git clone https://github.com/shivam5210/Agro.git
cd Agro
npm install

# Setup environment
cp .env.example .env
# Edit .env with your database credentials

# Setup database
npm run prisma:generate
npm run prisma:migrate
npm run prisma:seed

# Start development
npm run dev:all
```

Access at:
- Frontend: http://localhost:3000
- Backend: http://localhost:4000
- API Docs: http://localhost:4000/api-docs

### Docker Setup

```bash
# Build and start
docker-compose up --build

# Initialize database
docker-compose exec api npm run prisma:migrate
docker-compose exec api npm run prisma:seed
```

---

## 🔑 Default Credentials

| Role | Email | Password |
|------|-------|----------|
| Super Admin | admin@fpomarketlink.gov.in | Admin@123 |

> ⚠️ Change these in production!

---

## 📚 Available Scripts

```bash
npm run dev:all              # Start both services
npm run dev:api              # Start backend
npm run dev:web              # Start frontend
npm run build:all            # Build for production
npm run prisma:generate      # Generate Prisma client
npm run prisma:migrate       # Run migrations
npm run prisma:seed          # Seed database
npm test                     # Run tests
npm run lint                 # Run linting
```

---

## 🗄️ Database Setup

### PostgreSQL Setup

```bash
# Create database
psql -U postgres
CREATE DATABASE fpo_platform;
CREATE USER fpo_user WITH PASSWORD 'fpo_password';
GRANT ALL PRIVILEGES ON DATABASE fpo_platform TO fpo_user;
```

---

## 🔐 Security Checklist

- [ ] Change default admin password
- [ ] Generate secure JWT_SECRET
- [ ] Use HTTPS in production
- [ ] Restrict database access
- [ ] Rotate API keys

---

## 🚨 Troubleshooting

### Database Connection Error
```bash
# Check PostgreSQL is running
psql -U postgres
```

### Port Already in Use
```bash
# Kill process on port 4000
lsof -ti:4000 | xargs kill -9
```

---

**For detailed setup, see** [SETUP_GUIDE.md](./SETUP_GUIDE.md)
