# Axora ⚡

> A modern community platform for builders, developers, and creators.

[🚀 Live Demo](https://axora-lake.vercel.app) · [📦 GitHub Repository](https://github.com/reyncore/axora)

Axora is a full-stack social platform built for people who build things.

It combines social networking, developer-focused communities, direct messaging,
content discovery, bookmarks, notifications, media sharing, and progressive
web app support into one platform.

---

## ✨ Features

### 🏠 Social Platform

- 📝 Create and manage posts
- 💬 Replies and comments
- ❤️ Like posts
- 👥 Follow and unfollow users
- 👤 Public user profiles
- 🔎 Explore and search content
- 📄 Paginated feeds

### 💬 Communication

- 💬 One-to-one direct messaging
- 🔔 Real-time-ready notification architecture
- 📢 Activity notifications
- ⚙️ Notification preferences

### 🔖 Bookmarks

- 🔖 Save posts for later
- 📚 Create bookmark collections
- 🗂️ Organize saved content
- 🌐 Public bookmark collections

### 🖼️ Media

- Image uploads
- Video media support
- GIF support
- S3-compatible object storage
- Cloudflare R2 support

### ⚙️ Account & Personalization

- 🔐 Authentication
- 🔑 Password recovery
- 👤 Profile management
- 🎨 Appearance settings
- 🌙 Dark / light / system theme
- 🔔 Notification preferences

### 🛡️ Platform & Moderation

- Admin functionality
- User moderation
- Banned-user handling
- Rate limiting
- Input validation
- Security headers
- Protected API routes

### 📱 Progressive Web App

Axora is designed with PWA support so the platform can provide a more app-like experience on supported devices.

---

## 🧱 Tech Stack

| Category | Technology |
| --- | --- |
| Framework | Next.js 15 |
| Language | TypeScript |
| UI | React |
| Styling | Tailwind CSS |
| Authentication | Auth.js |
| Database | PostgreSQL |
| ORM | Prisma |
| Validation | Zod |
| Media Storage | S3-compatible storage / Cloudflare R2 |
| Runtime | Node.js |
| Deployment | Vercel-compatible |
| PWA | Web App Manifest / PWA support |

---

## 🏗️ Architecture

Axora follows a full-stack Next.js architecture.

```text
┌───────────────────────────────────────────┐
│                  Axora                    │
├───────────────────────────────────────────┤
│                                           │
│              Next.js / React              │
│                    │                      │
│          ┌─────────┴─────────┐            │
│          │                   │            │
│       UI Layer           API Routes       │
│          │                   │            │
│          └─────────┬─────────┘            │
│                    │                      │
│               Business Logic              │
│                    │                      │
│          ┌─────────┴─────────┐            │
│          │                   │            │
│       Prisma             Storage          │
│          │                   │            │
│      PostgreSQL       S3 / Cloudflare R2  │
│                                           │
└───────────────────────────────────────────┘
```

---

## 📁 Project Structure

```text
src/
├── app/
│   ├── (auth)/                  # Authentication pages
│   ├── (main)/                  # Main application
│   │   ├── bookmarks/           # Bookmarks & collections
│   │   ├── explore/             # Explore & discovery
│   │   ├── messages/            # Direct messages
│   │   ├── notifications/       # Notifications
│   │   ├── profile/             # User profiles
│   │   ├── settings/            # Account & appearance settings
│   │   └── ...
│   │
│   └── api/                     # API routes
│
├── components/                  # Reusable UI components
├── hooks/                       # Custom React hooks
├── lib/                         # Utilities & server logic
└── types/                       # Shared TypeScript types
```

---

# 🚀 Getting Started

## Prerequisites

Make sure you have:

- Node.js 18+
- PostgreSQL
- npm
- A configured object-storage provider for media
- Required environment variables

---

## 1. Clone the repository

```bash
git clone https://github.com/reyncore/axora.git
cd axora
npm install
```

---

## 2. Configure environment variables

Create your local environment file:

```bash
cp .env.example .env.local
```

Then configure the required variables inside `.env.local`.

Depending on your environment, Axora may require configuration for:

- PostgreSQL
- Authentication
- Object storage
- Cloudflare R2 / S3
- Email
- Redis / rate limiting
- Application URL

> Never commit `.env.local` or production credentials to Git.

---

## 3. Configure the database

Make sure PostgreSQL is running and your `DATABASE_URL` points to the correct database.

Example:

```env
DATABASE_URL="postgresql://username:password@localhost:5432/axora"
```

---

## 4. Generate Prisma Client

```bash
npm run db:generate
```

---

## 5. Push the database schema

For local development:

```bash
npm run db:push
```

If the project seed is configured:

```bash
npm run db:seed
```

---

## 6. Start the development server

```bash
npm run dev
```

Then open:

```text
http://localhost:3000
```

---

# 🛠️ Development Commands

```bash
# Development
npm run dev

# Production build
npm run build

# Type checking
npm run type-check

# Prisma
npm run db:generate
npm run db:push
npm run db:migrate
npm run db:studio
npm run db:seed
npm run db:reset
```

> ⚠️ `db:reset` is destructive and should never be used against a production database.

---

# 🔐 Security

Axora includes multiple application-level security mechanisms.

### Authentication

- Auth.js-based authentication
- Protected application routes
- HTTP-only session cookies
- Password hashing

### Input Security

- Zod schema validation
- Server-side validation
- Authorization checks
- Protected API endpoints

### Upload Security

Uploaded media is validated server-side instead of relying only on the client-provided MIME type.

### Rate Limiting

Rate limiting is applied to sensitive operations to reduce abuse and automated attacks.

### Additional Protection

- Security response headers
- User moderation
- Ban handling
- Soft deletion where applicable
- Server-side authorization

---

# 🗺️ Roadmap

## ✅ Available

- [x] Authentication
- [x] Registration
- [x] Password recovery
- [x] Social feed
- [x] Posts
- [x] Replies
- [x] Comments
- [x] Likes
- [x] Follow system
- [x] User profiles
- [x] Search / Explore
- [x] Notifications
- [x] Notification preferences
- [x] Direct messaging
- [x] Bookmarks
- [x] Bookmark collections
- [x] Public collections
- [x] Media uploads
- [x] Image support
- [x] Video support
- [x] GIF support
- [x] Account settings
- [x] Appearance settings
- [x] PWA support
- [x] Admin / moderation features
- [x] Rate limiting

## 🚧 In Progress

- [ ] Improve real-time communication
- [ ] Improve real-time notification delivery
- [ ] Improve search and discovery
- [ ] Improve mobile experience
- [ ] Improve platform performance

## 🔮 Planned

- [ ] Advanced creator features
- [ ] Advanced community discovery
- [ ] More moderation tools
- [ ] Platform analytics
- [ ] Additional integrations

> The roadmap is subject to change as Axora evolves.

---

# 🤝 Contributing

Contributions, ideas, bug reports, and feedback are welcome.

### Development workflow

1. Fork the repository.
2. Create a feature branch.

```bash
git checkout -b feature/my-feature
```

3. Make your changes.
4. Run the relevant checks.

```bash
npm run type-check
npm run build
```

5. Commit your changes.

```bash
git commit -m "feat: add my feature"
```

6. Push your branch.

```bash
git push origin feature/my-feature
```

7. Open a Pull Request.

For larger features, opening an issue first is recommended so the implementation can be discussed before development begins.

---

# 🧭 Project Goals

Axora is being built around a simple idea:

> **Give builders a place to share what they are building, discover other builders, save useful resources, and have meaningful conversations.**

The long-term goal is to create a community platform that is useful for:

- 👨‍💻 Developers
- 🎨 Creators
- 🧑‍🎓 Students
- 🚀 Indie hackers
- 🛠️ Builders
- 🌱 Open-source contributors

---

# 📌 Project Status

Axora is an actively developed project.

The platform is evolving rapidly, so APIs, database schemas, UI components, and features may change between versions.

If you are experimenting with the project, use the latest version of the repository and check the documentation before deploying it to production.

---

# 📄 License

A license has not yet been finalized for this repository.

Until a license is added, do not assume that the code is available for unrestricted redistribution, modification, or commercial use.

---

# 👨‍💻 Author

Built by **[reyncore](https://github.com/reyncore)**.

---

<p align="center">
  Built with ☕, TypeScript, and a lot of debugging.
</p>
