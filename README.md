# NLW Agents - Rocketseat 25

A full-stack referral and Q&A system built for events, featuring intelligent agents for automated question-answering and a comprehensive ranking system for referrals.

## 🚀 Overview

NLW Agents is a comprehensive platform that combines event registration with referral tracking and AI-powered Q&A functionality. Users can subscribe to events, invite others through referral links, and interact with AI agents to get answers to their questions.

## ✨ Features

### 🎯 Core Features
- **Event Subscription System** - Register users for events with email validation
- **Referral Program** - Track invitations and maintain referral rankings
- **AI-Powered Q&A** - Create rooms for questions and get AI-generated responses
- **Audio Recording** - Record audio questions for enhanced interaction
- **Real-time Ranking** - Live leaderboard for referral performance

### 🔧 Technical Features
- **REST API** - Complete backend API with Swagger documentation
- **Real-time Data** - Redis-backed ranking and caching system
- **Database Management** - PostgreSQL with Drizzle ORM
- **Modern Frontend** - React 19 with TypeScript and TailwindCSS
- **Container Support** - Docker Compose for easy deployment

## 🛠️ Tech Stack

### Backend
- **Runtime**: Node.js with TypeScript
- **Framework**: Fastify
- **Database**: PostgreSQL with Drizzle ORM
- **Cache**: Redis
- **Validation**: Zod
- **Authentication**: JWT
- **Documentation**: Swagger/OpenAPI

### Frontend
- **Framework**: React 19
- **Language**: TypeScript
- **Styling**: TailwindCSS
- **State Management**: TanStack React Query
- **Routing**: React Router DOM
- **UI Components**: Radix UI + Shadcn/ui
- **Forms**: React Hook Form with Zod validation
- **Icons**: Lucide React

### DevOps
- **Containerization**: Docker Compose
- **Code Quality**: Biome (linting & formatting)
- **Build Tool**: Vite (frontend) + tsup (backend)

## 📁 Project Structure

```
├── backend/                 # API server
│   ├── src/
│   │   ├── drizzle/        # Database schema and migrations
│   │   ├── functions/      # Business logic
│   │   ├── routes/         # API endpoints
│   │   ├── redis/          # Redis client configuration
│   │   └── server.ts       # Server entry point
│   ├── docker-compose.yml  # Infrastructure services
│   └── package.json
│
├── frontend/               # React application
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── pages/          # Page components
│   │   ├── http/           # API client and types
│   │   ├── lib/            # Utilities
│   │   └── main.tsx        # App entry point
│   └── package.json
│
└── README.md              # This file
```

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- Docker and Docker Compose
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd nlw-agents-rocketseat-25
   ```

2. **Start the infrastructure services**
   ```bash
   cd backend
   docker-compose up -d
   ```

3. **Set up the backend**
   ```bash
   # Install dependencies
   npm install
   
   # Set up environment variables
   cp .env.example .env
   # Edit .env with your configuration
   
   # Run database migrations
   npm run db:migrate
   
   # Start development server
   npm run dev
   ```

4. **Set up the frontend**
   ```bash
   cd ../frontend
   
   # Install dependencies
   npm install
   
   # Start development server
   npm run dev
   ```

### Environment Variables

Create a `.env` file in the backend directory:

```env
# Server
PORT=3333

# Database
DATABASE_URL=postgresql://docker:docker@localhost:5432/connect

# Redis
REDIS_URL=redis://localhost:6379

# URLs
API_URL=http://localhost:3333
WEB_URL=http://localhost:5173
```

## 🎮 Usage

### API Endpoints

The backend provides several key endpoints:

- `POST /subscriptions` - Subscribe to events
- `GET /ranking` - Get referral rankings
- `GET /invites/:subscriberId` - Access referral links
- `GET /subscribers/:id/ranking/*` - Get subscriber metrics

### Frontend Routes

- `/` - Home page with room listing
- `/create-room` - Create new Q&A rooms
- `/room/:roomId` - Q&A room interface
- `/room/:roomId/audio` - Audio recording interface

### Development

**Backend Development**
```bash
cd backend
npm run dev          # Start with hot reload
npm run db:generate  # Generate database migrations
npm run db:migrate   # Run migrations
npm run build        # Build for production
```

**Frontend Development**
```bash
cd frontend
npm run dev          # Start development server
npm run build        # Build for production
npm run preview      # Preview production build
```

## 📊 Key Features Explained

### Referral System
- Users can invite others through unique referral links
- Referrals are tracked and scored using Redis
- Real-time ranking system shows top referrers
- Automatic scoring when referrals are successful

### Q&A System
- Create rooms for organized question sessions
- AI-powered responses to user questions
- Audio recording capabilities for enhanced interaction
- Real-time question management

### Database Schema
- `subscriptions` table for user management
- Redis for high-performance ranking data
- Drizzle ORM for type-safe database operations

## 🔧 API Documentation

Once running, visit `http://localhost:3333/docs` to access the interactive Swagger documentation.

## 🐳 Docker Support

The project includes Docker Compose configuration for easy infrastructure setup:

```bash
cd backend
docker-compose up -d  # Starts PostgreSQL and Redis
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is part of the NLW (Next Level Week) event by Rocketseat.

## 🎯 Event Information

This project was developed during NLW Agents event by Rocketseat, demonstrating modern web development practices with intelligent agents and real-time systems. 