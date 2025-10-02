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

FumbleWorks is a cutting-edge AI-powered video call application that revolutionizes how you conduct and manage meetings. From real-time AI assistance during calls to comprehensive post-meeting analytics, FumbleWorks provides a complete meeting experience.

### ✨ Key Features

🤖 **AI-Powered Video Calls** - Intelligent assistance during your meetings  
🧠 **Custom Real-time Agents** - Tailored AI agents for specific use cases  
📞 **Stream Video SDK** - High-quality, reliable video communication  
💬 **Stream Chat SDK** - Integrated chat functionality  
📝 **Summaries & Transcripts** - Automated meeting documentation  
📂 **Meeting History** - Complete meeting management and tracking  
🔍 **Transcript Search** - Find specific moments in your meetings  
📺 **Video Playback** - Review meetings with synchronized transcripts  
💬 **AI Meeting Q&A** - Ask questions about your meeting content  
🧠 **OpenAI Integration** - Powered by advanced language models  
💳 **Polar Subscriptions** - Flexible subscription management  
🔐 **Better Auth** - Secure authentication system  
📱 **Mobile Responsive** - Perfect experience on all devices  

## 🚀 Tech Stack

### Frontend
- **Next.js 15** - React framework with App Router
- **React 19** - Latest React features and optimizations
- **TypeScript** - Type-safe development
- **Tailwind CSS v4** - Modern utility-first styling
- **Shadcn/ui** - Beautiful, accessible components

### Backend & Services
- **Stream Video SDK** - Real-time video communications
- **Stream Chat SDK** - Messaging and chat features
- **OpenAI API** - AI-powered features and analysis
- **Better Auth** - Authentication and session management
- **Drizzle ORM** - Type-safe database operations
- **PostgreSQL** - Robust relational database

### Infrastructure
- **Inngest** - Background job processing
- **Polar** - Subscription and billing management
- **CodeRabbit** - AI-assisted code reviews
- **Vercel** - Deployment and hosting (recommended)

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18.17 or later)
- **npm**, **yarn**, **pnpm**, or **bun**
- **PostgreSQL** database
- **Git**

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

Copy the environment file and configure your variables:

```bash
cp .env.example .env.local
```

Fill in your environment variables:

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/fumbleworks"

# Stream API
STREAM_API_KEY="your_stream_api_key"
STREAM_SECRET="your_stream_secret"

# OpenAI
OPENAI_API_KEY="your_openai_api_key"

# Polar (for subscriptions)
POLAR_ACCESS_TOKEN="your_polar_access_token"

# Better Auth
AUTH_SECRET="your_auth_secret"

# Inngest
INNGEST_EVENT_KEY="your_inngest_event_key"
INNGEST_SIGNING_KEY="your_inngest_signing_key"
```

### 4. Database Setup

Generate and run database migrations:

```bash
npm run db:generate
npm run db:migrate
```

### 5. Start Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to see the application.

## 📁 Project Structure

```
fumbleworks/
├── src/
│   ├── app/                 # Next.js App Router pages
│   │   ├── (auth)/         # Authentication routes
│   │   ├── api/            # API routes
│   │   └── globals.css     # Global styles
│   ├── components/         # Reusable UI components
│   │   └── ui/            # Shadcn/ui components
│   ├── db/                # Database configuration
│   │   ├── schema.ts      # Database schema
│   │   └── index.ts       # Database connection
│   ├── hooks/             # Custom React hooks
│   ├── lib/               # Utility libraries
│   │   ├── auth.ts        # Authentication configuration
│   │   ├── auth-client.ts # Client-side auth
│   │   └── utils.ts       # Utility functions
│   └── modules/           # Feature modules
│       └── auth/          # Authentication module
├── public/                # Static assets
├── drizzle/              # Database migrations
├── .env.example          # Environment variables template
├── drizzle.config.ts     # Database configuration
├── next.config.ts        # Next.js configuration
├── tailwind.config.ts    # Tailwind CSS configuration
└── tsconfig.json         # TypeScript configuration
```

## 🛠️ Available Scripts

```bash
# Development
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
npm run type-check   # Run TypeScript checks

# Database
npm run db:generate  # Generate database migrations
npm run db:migrate   # Run database migrations
npm run db:push      # Push schema changes
npm run db:studio    # Open Drizzle Studio
```

## 🔧 Configuration

### Authentication Setup

FumbleWorks uses Better Auth for secure authentication. Configure your auth settings in [`src/lib/auth.ts`](src/lib/auth.ts):

```typescript
export const auth = betterAuth({
  emailAndPassword: {
    enabled: true,
  },
  database: drizzleAdapter(db, {
    provider: "pg", 
    schema: {
      ...schema,
    },
  }),
});
```

### Stream Configuration

Set up your Stream Video and Chat SDKs with your API credentials in the environment variables.

### OpenAI Integration

Configure OpenAI for AI-powered features by adding your API key to the environment variables.

## 🚀 Deployment

### Deploy on Vercel (Recommended)

1. Push your code to GitHub
2. Connect your repository to [Vercel](https://vercel.com)
3. Configure environment variables in Vercel dashboard
4. Deploy automatically on every push to main branch

### Environment Variables for Production

Ensure all environment variables are properly set in your production environment:

- Database connection string
- Stream API credentials
- OpenAI API key
- Authentication secrets
- Subscription service credentials

## 🧪 Testing

```bash
# Run tests
npm run test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage
```

## 📚 API Documentation

### Authentication Endpoints

- `POST /api/auth/sign-up` - User registration
- `POST /api/auth/sign-in` - User login
- `POST /api/auth/sign-out` - User logout

### Meeting Endpoints

- `GET /api/meetings` - List user meetings
- `POST /api/meetings` - Create new meeting
- `GET /api/meetings/[id]` - Get meeting details
- `POST /api/meetings/[id]/transcript` - Generate transcript

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

### Development Workflow

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes
4. Run tests: `npm run test`
5. Commit your changes: `git commit -m 'Add amazing feature'`
6. Push to the branch: `git push origin feature/amazing-feature`
7. Open a Pull Request

### Code Review Process

- All PRs are automatically reviewed by CodeRabbit AI
- Manual review by maintainers
- Ensure all tests pass
- Follow our coding standards

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙋‍♂️ Support

- 📧 Email: support@fumbleworks.com
- 💬 Discord: [Join our community](https://discord.gg/fumbleworks)
- 📖 Documentation: [docs.fumbleworks.com](https://docs.fumbleworks.com)
- 🐛 Issues: [GitHub Issues](https://github.com/yourusername/fumbleworks/issues)

## 🎯 Roadmap

- [ ] **Q1 2024**: Advanced AI agent customization
- [ ] **Q2 2024**: Multi-language transcript support
- [ ] **Q3 2024**: Integration with popular calendar apps
- [ ] **Q4 2024**: Advanced analytics and insights

## 🌟 Acknowledgments

- [Stream](https://getstream.io/) for video and chat infrastructure
- [OpenAI](https://openai.com/) for AI capabilities
- [Vercel](https://vercel.com/) for hosting and deployment
- [Shadcn/ui](https://ui.shadcn.com/) for beautiful components

---

<div align="center">
  <p>Built with ❤️ by the FumbleWorks team</p>
  <p>
    <a href="https://fumbleworks.com">Website</a> •
    <a href="https://twitter.com/fumbleworks">Twitter</a> •
    <a href="https://linkedin.com/company/fumbleworks">LinkedIn</a>
  </p>
</div>