# MarketSync - Getting Started

## Installation Complete! ✅

Your MarketSync project has been successfully created with all dependencies installed.

## Quick Start (5 Minutes)

### 1. Start PostgreSQL Database
```bash
# If you have PostgreSQL installed locally
psql -U postgres
# Then run:
CREATE DATABASE marketsync;

# Or use Docker
docker run --name marketsync-db -e POSTGRES_PASSWORD=password -d -p 5432:5432 postgres:14
```

### 2. Start Redis Cache
```bash
# If you have Redis installed
redis-server

# Or use Docker
docker run --name marketsync-redis -d -p 6379:6379 redis:7
```

### 3. Terminal 1 - Start Backend Server
```bash
cd MarketSync/backend
npm run start:dev
```
✅ Backend will run on `http://localhost:3001`

### 4. Terminal 2 - Start Frontend Development Server
```bash
cd MarketSync/frontend
npm run dev
```
✅ Frontend will run on `http://localhost:3000`

### 5. Open in Browser
Visit: **http://localhost:3000**

## Project Structure

```
MarketSync/
├── frontend/               # Next.js PWA
│   ├── src/app/           # Pages
│   ├── src/components/    # React components
│   ├── src/lib/           # Utilities
│   └── package.json
│
├── backend/               # Nest.js API
│   ├── src/
│   │   ├── auth/          # Authentication
│   │   ├── platforms/     # Platform integrations
│   │   ├── campaigns/     # Campaign management
│   │   ├── analytics/     # Analytics engine
│   │   └── main.ts        # Entry point
│   ├── prisma/            # Database schema
│   └── package.json
│
├── docs/                  # Documentation
└── INSTALLATION_SUMMARY.md
```

## Environment Configuration

### Backend (.env)
Already configured with defaults. Update if needed:
```bash
cd backend
# Edit .env file
DATABASE_URL=postgresql://user:password@localhost:5432/marketsync
REDIS_HOST=localhost
REDIS_PORT=6379
JWT_SECRET=your-secure-secret-here
```

### Frontend (.env.local)
Already configured with defaults:
```bash
cd frontend
# .env.local is ready to use
NEXT_PUBLIC_API_URL=http://localhost:3001/api/v1
```

## Available Commands

### Frontend
```bash
cd frontend
npm run dev              # Start development server
npm run build            # Create production build
npm run lint             # Run ESLint
npm run test             # Run tests
```

### Backend
```bash
cd backend
npm run start:dev        # Start with hot reload
npm run start:debug      # Debug mode
npm run build            # Compile
npm run test             # Run tests
npm run test:cov         # Coverage report
```

## Database Setup (Optional - For Later)

When you're ready to set up the database schema:
```bash
cd backend
npx prisma migrate dev --name init
npx prisma generate
```

This will:
- Create all tables from the schema
- Set up relationships
- Generate Prisma client

## Next Steps

1. **Create AppModule** - Backend needs a main app module
2. **Set up authentication** - JWT and OAuth flows
3. **Connect to platforms** - Google, LinkedIn, Facebook, etc.
4. **Build dashboard** - Main UI components
5. **Implement campaigns** - Core feature

## Troubleshooting

### Port already in use?
```bash
# Find process using port 3000
lsof -i :3000
# Kill it
kill -9 <PID>
```

### PostgreSQL not running?
```bash
# Start PostgreSQL service
# Windows:
net start postgresql-x64-14

# Mac:
brew services start postgresql

# Linux:
sudo service postgresql start
```

### Node modules issues?
```bash
# Clean and reinstall
rm -rf node_modules package-lock.json
npm install
```

## Documentation

- **Setup Guide:** `../SETUP_GUIDE.md`
- **Project Files:** `../PROJECT_FILES.md`
- **Product Requirements:** `../MarketingPWA.txt`
- **AI Instructions:** `../.github/copilot-instructions.md`

## Support

Check the `INSTALLATION_SUMMARY.md` file for detailed information about:
- Installed dependencies
- Configuration files created
- Known issues
- Security considerations

---

**Ready to develop?** Start the servers and visit http://localhost:3000 🚀
