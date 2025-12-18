# StudyLink

This is a DBMS Project for our course. StudyLink is a collaborative learning platform where students can create groups, start discussions, share files, and interact with each other.

## Tech Stack

- **Frontend**: React + TypeScript + Vite + TailwindCSS
- **Backend**: Express + TypeScript + Prisma
- **Database**: PostgreSQL
- **Authentication**: Better Auth
- **File Upload**: UploadThing
- **Email**: Resend

## Prerequisites

- Node.js (v18 or higher)
- PostgreSQL (v14 or higher)
- npm or yarn

## Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/mehirk/study-link.git
cd study-link
```

### 2. Setup Backend

```bash
cd backend
npm install

# Copy environment variables template
cp .env.example .env

# Edit .env file with your actual values
# You'll need:
# - DATABASE_URL (PostgreSQL connection string)
# - RESEND_API_KEY (for email verification)
# - FRONTEND_URL (your frontend URL)
# - PORT (default: 3000)

# Generate Prisma client
npm run db:generate

# Run database migrations
npm run db:migrate

# Start the backend server
npm run dev
```

### 3. Setup Frontend

```bash
cd ../frontend
npm install

# Copy environment variables template
cp .env.example .env

# Edit .env file with your API URLs
# VITE_API_URL - Production API URL
# VITE_DEV_API_URL - Development API URL (usually http://localhost:3000)

# Start the frontend development server
npm run dev
```

### 4. Setup Database

1. Install PostgreSQL if you haven't already
2. Create a new database:
   ```sql
   CREATE DATABASE studylink;
   ```
3. Update the `DATABASE_URL` in `backend/.env` with your database credentials:
   ```
   DATABASE_URL="postgresql://username:password@localhost:5432/studylink?schema=public"
   ```
4. Run migrations:
   ```bash
   cd backend
   npm run db:migrate
   ```

## Environment Variables

### Backend (.env)
- `DATABASE_URL` - PostgreSQL connection string (required)
- `PORT` - Server port (default: 3000)
- `FRONTEND_URL` - Frontend URL for CORS (required)
- `RESEND_API_KEY` - Resend API key for email verification (required)

### Frontend (.env)
- `VITE_API_URL` - Production API URL (required)
- `VITE_DEV_API_URL` - Development API URL (required)

## Available Scripts

### Backend
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run db:generate` - Generate Prisma client
- `npm run db:migrate` - Run database migrations
- `npm run db:studio` - Open Prisma Studio
- `npm run db:push` - Push schema to database

### Frontend
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

## Project Structure

```
StudyLink-main/
├── backend/          # Express + TypeScript backend
│   ├── src/
│   │   ├── routes/   # API routes
│   │   ├── middlewares/  # Express middlewares
│   │   ├── utils/    # Utility functions
│   │   └── prisma/   # Prisma schema
│   └── package.json
├── frontend/         # React + TypeScript frontend
│   ├── src/
│   │   ├── components/  # React components
│   │   ├── pages/    # Page components
│   │   ├── lib/      # Utilities and API clients
│   │   └── hooks/    # Custom React hooks
│   └── package.json
└── docker-compose.yml  # Docker configuration
```

## Features

- User authentication and authorization
- Group creation and management
- Discussion threads within groups
- File uploads and sharing
- Real-time chat/discussions
- User profiles
- Private and public groups

## Contributing

This is a course project. For contributions, please contact the maintainers.

## License

ISC
