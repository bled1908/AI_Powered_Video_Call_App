# FumbleWorks

<div align="center">
  <img src="public/logo.svg" alt="FumbleWorks Logo" width="120" height="120" />
  
  <h3>AI-Powered Video Call Platform</h3>
  
  <p>Transform your meetings with intelligent video calls, real-time AI agents, and comprehensive post-call experiences.</p>
  
  [![Next.js](https://img.shields.io/badge/Next.js-15-black)](https://nextjs.org/)
  [![React](https://img.shields.io/badge/React-19-blue)](https://reactjs.org/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.0+-blue)](https://www.typescriptlang.org/)
  [![Tailwind CSS](https://img.shields.io/badge/Tailwind-v4-38B2AC)](https://tailwindcss.com/)
  [![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
</div>

---

## 🌟 Overview

FumbleWorks is a cutting-edge AI-powered video call application built from the ground up to revolutionize how you conduct and manage meetings. This comprehensive platform provides real-time AI assistance during calls, automated summaries and transcripts through background jobs, and a complete post-call experience including video playback, transcript search, and AI chat that understands meeting context.

### ✨ Key Features

🤖 **AI-Powered Video Calls** - Real-time intelligent assistance during meetings  
🧠 **Custom Real-time Agents** - Tailored AI agents for specific use cases  
📞 **Stream Video SDK** - High-quality, reliable video communication  
💬 **Stream Chat SDK** - Integrated real-time chat functionality  
📝 **Summaries & Transcripts** - Automated meeting documentation via background jobs  
📂 **Meeting History & Statuses** - Complete meeting management and tracking  
🔍 **Transcript Search** - Find specific moments and topics in meetings  
📺 **Video Playbook** - Review meetings with synchronized transcripts  
💬 **AI Meeting Q&A** - Contextual AI chat about meeting content  
🧠 **OpenAI Integration** - Advanced AI capabilities and analysis  
💳 **Polar Subscriptions** - Flexible subscription and billing management  
🔐 **Better Auth** - Secure multi-provider authentication  
📱 **Mobile Responsive** - Optimized experience across all devices  
🌐 **Next.js 15 + React 19** - Latest web technologies  
🎨 **Tailwind v4 + Shadcn/ui** - Modern design system  
⚙️ **Inngest Background Jobs** - Reliable background processing  
🧑‍💻 **CodeRabbit PR Reviews** - AI-assisted code review workflow  

## 🚀 Tech Stack

### Frontend
- **Next.js 15** - React framework with App Router and Server Components
- **React 19** - Latest React with concurrent features
- **TypeScript** - Full type safety across the application
- **Tailwind CSS v4** - Modern utility-first CSS framework
- **Shadcn/ui** - Beautiful, accessible component library
- **React Hook Form** - Performant form handling with validation
- **Zod** - TypeScript-first schema validation

### Backend & Services
- **Stream Video SDK** - Enterprise-grade video communications
- **Stream Chat SDK** - Real-time messaging and chat
- **OpenAI API** - GPT-4 powered AI features and analysis
- **Better Auth** - Modern authentication with multiple providers
- **PostgreSQL** - Robust relational database
- **Drizzle ORM** - Type-safe database operations

### Infrastructure & Tools
- **Inngest** - Reliable background job processing for transcripts
- **Polar** - Subscription management and billing
- **CodeRabbit** - AI-powered code review automation
- **Vercel** - Optimized deployment and hosting
- **Lucide React** - Beautiful, consistent icons
- **React Icons** - Extended icon library

## 📋 Prerequisites

Before you begin, ensure you have:

- **Node.js** (v18.17 or later)
- **npm**, **yarn**, **pnpm**, or **bun**
- **PostgreSQL** database (local or hosted)
- **Git** for version control

## ⚡ Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/fumbleworks.git
cd fumbleworks
```

### 2. Install Dependencies

```bash
npm install
# or
yarn install
# or
pnpm install
# or
bun install
```

### 3. Environment Setup

Copy the environment template and configure your variables:

```bash
cp .env.example .env.local
```

Configure your environment variables:

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/fumbleworks"

# Stream API (Video & Chat)
NEXT_PUBLIC_STREAM_API_KEY="your_stream_api_key"
STREAM_SECRET="your_stream_secret"

# OpenAI
OPENAI_API_KEY="your_openai_api_key"

# Better Auth
BETTER_AUTH_SECRET="your_better_auth_secret"
BETTER_AUTH_URL="http://localhost:3000"

# OAuth Providers (optional)
GOOGLE_CLIENT_ID="your_google_client_id"
GOOGLE_CLIENT_SECRET="your_google_client_secret"
GITHUB_CLIENT_ID="your_github_client_id"
GITHUB_CLIENT_SECRET="your_github_client_secret"

# Polar (Subscriptions)
POLAR_ACCESS_TOKEN="your_polar_access_token"

# Inngest (Background Jobs)
INNGEST_EVENT_KEY="your_inngest_event_key"
INNGEST_SIGNING_KEY="your_inngest_signing_key"
```

### 4. Database Setup

Set up your database schema:

```bash
npm run db:generate
npm run db:migrate
npm run db:seed # optional: add sample data
```

### 5. Start Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to access FumbleWorks.

## 📁 Project Structure

```
fumbleworks/
├── src/
│   ├── app/                    # Next.js 15 App Router
│   │   ├── (auth)/            # Auth route group
│   │   │   ├── sign-in/       # Sign in page
│   │   │   └── sign-up/       # Sign up page
│   │   ├── api/               # API routes
│   │   │   ├── auth/          # Authentication endpoints
│   │   │   ├── meetings/      # Meeting management
│   │   │   └── webhooks/      # External service webhooks
│   │   ├── dashboard/         # Main app dashboard
│   │   ├── meetings/          # Meeting-related pages
│   │   └── layout.tsx         # Root layout
│   ├── components/            # Reusable components
│   │   ├── ui/               # Shadcn/ui components
│   │   ├── forms/            # Form components
│   │   └── providers/        # Context providers
│   ├── db/                   # Database configuration
│   │   ├── schema.ts         # Drizzle schema definitions
│   │   └── index.ts          # Database connection
│   ├── hooks/                # Custom React hooks
│   ├── lib/                  # Utility libraries
│   │   ├── auth.ts           # Better Auth configuration
│   │   ├── auth-client.ts    # Client-side auth utilities
│   │   ├── stream.ts         # Stream SDK configuration
│   │   └── utils.ts          # General utilities
│   └── modules/              # Feature-based modules
│       ├── auth/             # Authentication module
│       │   └── ui/           # Auth UI components
│       │       └── views/    # Auth view components
│       ├── meetings/         # Meeting management
│       └── chat/             # Chat functionality
├── public/                   # Static assets
│   └── logo.svg             # FumbleWorks logo
├── drizzle/                 # Database migrations
├── inngest/                 # Background job functions
├── .env.example             # Environment template
├── drizzle.config.ts        # Database configuration
├── next.config.ts           # Next.js configuration
├── tailwind.config.ts       # Tailwind v4 configuration
├── components.json          # Shadcn/ui configuration
└── tsconfig.json            # TypeScript configuration
```

## 🛠️ Available Scripts

```bash
# Development
npm run dev              # Start development server with hot reload
npm run build            # Build optimized production bundle
npm run start            # Start production server
npm run lint             # Run ESLint with auto-fix
npm run type-check       # TypeScript type checking

# Database Operations
npm run db:generate      # Generate new migrations
npm run db:migrate       # Apply pending migrations
npm run db:push          # Push schema changes directly
npm run db:studio        # Open Drizzle Studio (database GUI)
npm run db:seed          # Seed database with sample data

# Background Jobs
npm run inngest:dev      # Start Inngest development server

# Testing & Quality
npm run test             # Run test suite
npm run test:watch       # Run tests in watch mode
npm run test:coverage    # Generate test coverage report
```

## 🔧 Configuration

### Authentication Setup

FumbleWorks uses Better Auth for comprehensive authentication:

```typescript
// src/lib/auth.ts
export const auth = betterAuth({
  database: drizzleAdapter(db, {
    provider: "pg",
    schema: authSchema,
  }),
  emailAndPassword: {
    enabled: true,
    requireEmailVerification: true,
  },
  socialProviders: {
    google: {
      clientId: process.env.GOOGLE_CLIENT_ID!,
      clientSecret: process.env.GOOGLE_CLIENT_SECRET!,
    },
    github: {
      clientId: process.env.GITHUB_CLIENT_ID!,
      clientSecret: process.env.GITHUB_CLIENT_SECRET!,
    },
  },
});
```

### Stream Video & Chat Configuration

Configure Stream services for video calls and real-time chat:

```typescript
// Client-side Stream configuration
const streamClient = new StreamVideoClient({
  apiKey: process.env.NEXT_PUBLIC_STREAM_API_KEY!,
  user: currentUser,
  token: streamUserToken,
});
```

### AI Integration

OpenAI powers the intelligent features:

```typescript
// AI service configuration
const openai = new OpenAI({
  apiKey: process.env.OPENAI_API_KEY,
});
```

## 🚀 Deployment

### Deploy on Vercel (Recommended)

1. **Prepare Repository**
   ```bash
   git add .
   git commit -m "Ready for deployment"
   git push origin main
   ```

2. **Deploy to Vercel**
   - Connect your GitHub repository to [Vercel](https://vercel.com)
   - Configure environment variables in the Vercel dashboard
   - Deploy automatically with every push to main

3. **Production Environment Variables**
   - Set all environment variables from `.env.example`
   - Configure production database URL
   - Set up production Stream API keys
   - Configure OAuth app credentials for production domain

### Database Setup for Production

Ensure your production database is properly configured:

```bash
# Run migrations in production
npm run db:migrate
```

## 🧪 Testing

```bash
# Run all tests
npm run test

# Run tests with coverage
npm run test:coverage

# Run specific test files
npm run test -- auth.test.ts

# Run tests in watch mode during development
npm run test:watch
```

## 📚 API Documentation

### Authentication Endpoints

- `POST /api/auth/sign-up` - User registration with email/password
- `POST /api/auth/sign-in` - User authentication
- `POST /api/auth/sign-out` - User logout
- `GET /api/auth/session` - Get current session
- `POST /api/auth/callback/google` - Google OAuth callback
- `POST /api/auth/callback/github` - GitHub OAuth callback

### Meeting Management

- `GET /api/meetings` - List user meetings with pagination
- `POST /api/meetings` - Create new meeting room
- `GET /api/meetings/[id]` - Get meeting details and participants
- `PUT /api/meetings/[id]` - Update meeting settings
- `POST /api/meetings/[id]/join` - Join meeting room
- `POST /api/meetings/[id]/leave` - Leave meeting room

### AI Features

- `POST /api/meetings/[id]/transcript` - Generate meeting transcript
- `POST /api/meetings/[id]/summary` - Create AI meeting summary
- `POST /api/ai/chat` - Chat with AI about meeting content
- `GET /api/meetings/[id]/insights` - Get AI-generated insights

## 🤝 Contributing

We welcome contributions to FumbleWorks! Please follow our contribution guidelines:

### Development Workflow

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes with proper testing**
4. **Run quality checks**
   ```bash
   npm run lint
   npm run type-check
   npm run test
   ```
5. **Commit with conventional commits**
   ```bash
   git commit -m "feat: add amazing feature"
   ```
6. **Push and create Pull Request**
   ```bash
   git push origin feature/amazing-feature
   ```

### Code Standards

- Follow TypeScript best practices
- Use Prettier for code formatting
- Write comprehensive tests for new features
- Follow component composition patterns
- Use proper error handling and loading states

### AI-Assisted Code Review

All pull requests are automatically reviewed by CodeRabbit AI for:
- Code quality and best practices
- Security vulnerabilities
- Performance optimizations
- TypeScript type safety

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support & Contact

Need help with FumbleWorks? We're here to assist you:

- 📧 **Email**: [bled19082005@gmail.com](mailto:bled19082005@gmail.com)
- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/yourusername/fumbleworks/issues)
- 💡 **Feature Requests**: [GitHub Discussions](https://github.com/yourusername/fumbleworks/discussions)
- 📖 **Documentation**: Check our comprehensive docs above

For technical support, please include:
- Node.js and npm versions
- Operating system details
- Error messages and logs
- Steps to reproduce the issue

## 🎯 Roadmap

### Phase 1 - Core Platform ✅
- [x] Real-time video calls with Stream SDK
- [x] Authentication with Better Auth
- [x] Basic meeting management
- [x] Mobile responsive design

### Phase 2 - AI Integration 🚧
- [x] OpenAI-powered transcriptions
- [x] AI meeting summaries
- [ ] Advanced AI chat with meeting context
- [ ] Custom AI agent personalities

### Phase 3 - Enhanced Features 📅
- [ ] Advanced transcript search with vector embeddings
- [ ] Multi-language support for transcripts
- [ ] Calendar integrations (Google, Outlook)
- [ ] Advanced meeting analytics and insights

### Phase 4 - Enterprise Features 📅
- [ ] Team workspaces and roles
- [ ] Advanced subscription tiers
- [ ] API for third-party integrations
- [ ] White-label solutions

## 🌟 Acknowledgments

Special thanks to the amazing tools and services that make FumbleWorks possible:

- **[Stream](https://getstream.io/)** - For robust video and chat infrastructure
- **[OpenAI](https://openai.com/)** - For powerful AI capabilities
- **[Vercel](https://vercel.com/)** - For seamless deployment and hosting
- **[Shadcn/ui](https://ui.shadcn.com/)** - For beautiful, accessible components
- **[Better Auth](https://www.better-auth.com/)** - For modern authentication
- **[Drizzle ORM](https://orm.drizzle.team/)** - For type-safe database operations

---

<div align="center">
  <p>Built with ❤️ for the future of video communications</p>
  <p>
    <strong>FumbleWorks</strong> - Where AI meets video calls
  </p>
  <p>
    <a href="mailto:bled19082005@gmail.com">Contact</a> •
    <a href="https://github.com/yourusername/fumbleworks">GitHub</a> •
    <a href="https://fumbleworks.com">Website</a>
  </p>
</div>