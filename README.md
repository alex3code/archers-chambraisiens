# New Archer - Archery Photo Gallery

A modern, clean photo gallery website built specifically for archery photography. Features user authentication, photo favorites, sharing capabilities, and admin photo management.

 **🌐 Live Website**: [https://archers-chambraisiens.com/](https://archers-chambraisiens.com/)


## 🏹 Features

- **Archery-focused**: Designed specifically for archery photography
- **Photo Gallery**: Browse photos in a responsive grid layout with lightbox viewing
- **Favorites System**: Users can favorite photos and maintain a personal collection
- **Photo Sharing**: Share photos via social media or direct links
- **User Authentication**: Secure login with Google OAuth and email
- **Admin Panel**: Admin-only photo upload and management
- **Clean Design**: Modern blue and white theme inspired by archery aesthetics
- **Responsive**: Fully responsive design for all devices

## 🛠️ Tech Stack

- **Framework**: Next.js 14 with App Router
- **Database**: PostgreSQL with Prisma ORM
- **Authentication**: NextAuth.js
- **Styling**: Tailwind CSS
- **File Storage**: Cloudinary
- **Deployment**: Vercel
- **TypeScript**: Full type safety

## 🚀 Getting Started

### Prerequisites

- Node.js (v18 or higher)
- PostgreSQL database (or use Supabase/PlanetScale)
- Cloudinary account
- Google OAuth credentials (optional)

### Installation

1. **Navigate to the project directory**
   ```bash
   cd C:\webdev\final-archer
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   ```bash
   copy .env.example .env.local
   ```
   
   Fill in your environment variables in `.env.local`:
   ```env
   DATABASE_URL="postgresql://username:password@localhost:5432/new_archer"
   NEXTAUTH_SECRET="your-secret-key-here"
   NEXTAUTH_URL="http://localhost:3000"
   CLOUDINARY_CLOUD_NAME="your-cloud-name"
   CLOUDINARY_API_KEY="your-api-key"
   CLOUDINARY_API_SECRET="your-api-secret"
   GOOGLE_CLIENT_ID="your-google-client-id"
   GOOGLE_CLIENT_SECRET="your-google-client-secret"
   ```

4. **Set up the database**
   ```bash
   npx prisma db push
   npx prisma generate
   ```

5. **Run the development server**
   ```bash
   npm run dev
   ```

6. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## 📊 Database Setup

### Using Supabase (Recommended)
1. Create a free account at [supabase.com](https://supabase.com)
2. Create a new project
3. Go to Settings > Database
4. Copy the connection string to your `.env.local` as `DATABASE_URL`

### PostgreSQL Local Setup
```bash
# Install PostgreSQL (Windows)
# Download from https://www.postgresql.org/download/windows/

# Create database
createdb new_archer
```

## ☁️ Cloudinary Setup

1. Create a free account at [cloudinary.com](https://cloudinary.com)
2. Get your Cloud name, API Key, and API Secret from the dashboard
3. Add them to your `.env.local`
4. Free tier includes 25GB storage and 25GB monthly bandwidth

## 🔐 Admin Setup

To make a user an admin:

1. Sign in to your application
2. Connect to your database
3. Set `isAdmin: true` for that user:
   ```sql
   UPDATE users SET "isAdmin" = true WHERE email = 'your-email@example.com';
   ```

## 🚀 Deployment on Vercel

1. **Push to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

2. **Deploy on Vercel**
   - Go to [vercel.com](https://vercel.com)
   - Import your GitHub repository
   - Add environment variables in Vercel dashboard
   - Deploy!

3. **Update NEXTAUTH_URL**
   ```env
   NEXTAUTH_URL="https://your-app.vercel.app"
   ```

## 📁 Project Structure

```
final-archer/
├── app/                    # Next.js App Router
│   ├── api/               # API routes
│   │   ├── auth/          # NextAuth configuration
│   │   └── favorites/     # Favorites API
│   ├── about/             # About page
│   ├── contact/           # Contact page
│   ├── favorites/         # User favorites page
│   ├── gallery/           # Gallery page
│   ├── layout.tsx         # Root layout
│   ├── page.tsx           # Homepage
│   └── globals.css        # Global styles
├── components/            # React components
│   ├── providers/         # Context providers
│   ├── Navigation.tsx     # Main navigation
│   ├── PhotoGrid.tsx      # Photo grid component
│   ├── FavoriteButton.tsx # Favorite functionality
│   └── ShareButton.tsx    # Share functionality
├── lib/                   # Utility functions
│   ├── prisma.ts          # Prisma client
│   ├── photos.ts          # Photo queries
│   └── utils.ts           # Utility functions
├── prisma/               # Database schema
│   └── schema.prisma      # Prisma schema
└── types/                # TypeScript definitions
    └── next-auth.d.ts     # NextAuth types
```

## 🎨 Design & Theme

The website uses a clean, modern design with:
- **Primary Colors**: Blue (#2563eb) and White
- **Typography**: Inter font family
- **Layout**: Responsive grid system
- **Components**: Clean, accessible UI components
- **Theme**: Inspired by archery aesthetics with professional sports feel

## 🔧 Development Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint
- `npx prisma db push` - Push database schema
- `npx prisma generate` - Generate Prisma client
- `npx prisma studio` - Open Prisma Studio

## 📈 Features in Detail

### Photo Management
- Admin can upload photos via Cloudinary
- Automatic image optimization and CDN delivery
- Responsive image loading with Next.js Image component
- Lightbox viewing with keyboard navigation

### User Experience
- Clean, modern interface inspired by archery
- Grid layout for photo browsing
- Lightbox with smooth transitions
- Social sharing integration
- Personal favorites collection

### Authentication
- Email-based login option
- Secure session management
- Role-based access control (Admin/User)


## Quick DB update
npx prisma db push --force-reset
npm run db:seed




**Created with ❤️ for the archery community** 🏹
