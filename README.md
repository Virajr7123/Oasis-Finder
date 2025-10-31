# 🌿 OasisFinder

**Find your pocket of peace in the city.**

OasisFinder is a sophisticated place discovery web application that helps users discover quiet parks, serene libraries, tranquil cafes, relaxing spas, peaceful yoga studios, and other serene spots to escape urban noise. With intuitive search functionality, real-time location services, and interactive mapping, users can find their perfect sanctuary in any city.

---

## 📋 Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Technology Stack](#technology-stack)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [API Routes](#api-routes)
- [Project Architecture](#project-architecture)
- [Creator](#creator)

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🌍 **Global Place Discovery** | Browse curated tranquil places from around the world with authentic Google Photos |
| 📍 **Location-Based Search** | Find peaceful places near your current location using geolocation API |
| 🔍 **Advanced Search** | Filter by place name, category, country, or address with real-time results |
| 🗺️ **Interactive Map View** | Visualize places on an interactive map with hover-to-focus functionality |
| 📋 **List View** | Browse places in a beautiful card-based grid layout |
| 🎨 **Dark/Light Theme** | Seamless theme switching with persistent user preference |
| ⚡ **Smart Caching** | Intelligent caching system prevents unnecessary API calls and improves performance |
| 📱 **Responsive Design** | Fully optimized for desktop, tablet, and mobile devices |
| 🔐 **Secure Authentication** | User authentication system with sign-up and sign-in pages |
| 🖼️ **Rich Media** | High-quality place photos with detailed information cards |

---

## 📁 Project Structure

\`\`\`
oasis-finder/
├── app/
│   ├── (protected)/              # Protected routes (authenticated users only)
│   │   ├── page.tsx              # Main dashboard
│   │   ├── layout.tsx            # Protected layout wrapper
│   │   ├── loading.tsx           # Loading state component
│   │   └── place/[id]/page.tsx   # Individual place detail page
│   ├── auth/                     # Authentication pages
│   │   ├── sign-in/page.tsx      # User login page
│   │   └── sign-up/page.tsx      # User registration page
│   ├── api/                      # API route handlers
│   │   ├── places/route.ts       # Search nearby places (Foursquare API)
│   │   ├── place-details/route.ts    # Fetch single place details
│   │   ├── place-photo/route.ts      # Retrieve place photos
│   │   ├── global-places-photos/route.ts # Get global places with photos
│   │   └── fsq-place-details/route.ts    # Foursquare place details
│   ├── layout.tsx                # Root layout component
│   ├── globals.css               # Global styles & theme configuration
│   └── loading.tsx               # Root loading state
├── components/                   # Reusable React components
│   ├── ui/                       # UI component library (shadcn/ui)
│   ├── place-card.tsx            # Place information card component
│   ├── map-view.tsx              # Interactive map display
│   ├── site-header.tsx           # Application header/navigation
│   └── ...                       # Additional components
├── contexts/                     # React Context API providers
│   └── theme-context.tsx         # Dark/Light theme context
├── hooks/                        # Custom React hooks
│   ├── use-geolocation.ts        # Geolocation functionality
│   ├── use-mobile.tsx            # Mobile detection hook
│   └── use-toast.ts              # Toast notification hook
├── lib/                          # Utility functions and data
│   ├── data.ts                   # Global places data
│   └── utils.ts                  # Helper utilities (cn function)
├── public/                       # Static assets
├── package.json                  # Dependencies and scripts
├── tsconfig.json                 # TypeScript configuration
├── next.config.mjs               # Next.js configuration
├── postcss.config.mjs            # PostCSS configuration
└── tailwind.config.js            # Tailwind CSS configuration
\`\`\`

---

## 🛠️ Technology Stack

| Layer | Technologies |
|-------|--------------|
| **Frontend Framework** | Next.js 15.2.4 (App Router) |
| **React Version** | React 19 with React DOM 19 |
| **Language** | TypeScript 5 |
| **Styling** | Tailwind CSS 4.1.9 with custom theme |
| **UI Components** | shadcn/ui with Radix UI |
| **Icons** | Lucide React 0.454.0 |
| **Form Handling** | React Hook Form 7.60.0 with Zod validation |
| **Maps & 3D** | Leaflet (or similar), Three.js, React Three Fiber |
| **Charts & Visualizations** | Recharts 2.15.4 |
| **Notifications** | Sonner 1.7.4 (toast notifications) |
| **State Management** | React Context API |
| **API Integration** | Foursquare API, Google Places API |
| **Build & Bundler** | Turbopack (Next.js 16) |
| **Package Manager** | npm |

---

## 🚀 Installation & Setup

### Prerequisites
- Node.js 18+ and npm installed
- Modern web browser with geolocation support
- API keys for:
  - Foursquare Places API
  - Google Places API
  - Google Photos API

### Steps

1. **Clone the Repository**
   \`\`\`bash
   git clone https://github.com/Virajr7123/Oasis-Finder
   \`\`\`

2. **Install Dependencies**
   \`\`\`bash
   npm install
   \`\`\`

3. **Configure Environment Variables**
   Create a `.env.local` file in the root directory:
   \`\`\`env
   NEXT_PUBLIC_FOURSQUARE_API_KEY=your_foursquare_key
   NEXT_PUBLIC_GOOGLE_PLACES_API_KEY=your_google_places_key
   NEXT_PUBLIC_GOOGLE_PHOTOS_API_KEY=your_google_photos_key
   \`\`\`

4. **Run Development Server**
   \`\`\`bash
   npm run dev
   \`\`\`
   Open [http://localhost:3000](http://localhost:3000) in your browser.

5. **Build for Production**
   \`\`\`bash
   npm run build
   npm start
   \`\`\`

---

## 💡 Usage

### For Users

1. **Sign Up / Sign In** - Create an account or log in to access the app
2. **Browse Global Places** - Explore tranquil places from around the world
3. **Search** - Use the search bar to filter by place type (spa, cafe, library, park, etc.)
4. **Find Nearby** - Click "Find Serenity Near Me" to discover places in your location
5. **Switch Views** - Toggle between List View and Map View
6. **View Details** - Click on any place card to see more information
7. **Theme Toggle** - Switch between light and dark themes

### For Developers

#### Running Tests
\`\`\`bash
npm run lint
\`\`\`

#### Building Locally
\`\`\`bash
npm run build
\`\`\`

#### Environment Setup
The app uses environment variables for API configuration. Ensure all keys are set before deployment.

---

## 🔌 API Routes

| Route | Method | Description |
|-------|--------|-------------|
| `/api/places` | GET | Search places near coordinates with optional query |
| `/api/place-details` | GET | Fetch detailed information for a single place |
| `/api/place-photo` | GET | Retrieve photos for a place |
| `/api/global-places-photos` | GET | Get pre-curated global places with photos |
| `/api/fsq-place-details` | GET | Get Foursquare-specific place details |

### Example API Calls

\`\`\`typescript
// Search nearby places
const response = await fetch('/api/places?lat=40.7128&lng=-74.0060&query=spa');

// Get place details
const details = await fetch('/api/place-details?placeId=123');

// Get global places
const global = await fetch('/api/global-places-photos');
\`\`\`

---

## 🏗️ Project Architecture

### Authentication Flow
\`\`\`
Sign In/Up → Authentication Check → Protected Routes → Main Dashboard
\`\`\`

### Data Flow
\`\`\`
User Search/Location → API Routes → External APIs (Foursquare, Google) 
→ Cache Layer → Frontend Display → Map/List View
\`\`\`

### Caching Strategy
- **Smart Caching**: Results are cached to prevent redundant API calls
- **Cache Key**: Based on latitude, longitude, and search query
- **Cache Invalidation**: Cleared on new search or manual refresh

### Theme System
- Uses React Context API for theme management
- Persistent theme preference stored in localStorage
- CSS custom properties for dynamic theme switching
- Separate styling for protected pages vs. auth pages

---

## 📊 Key Components

### Place Card (`components/place-card.tsx`)
Displays individual place information with image, rating, and quick actions.

### Map View (`components/map-view.tsx`)
Interactive map showing place locations with hover-to-focus and geolocation marker.

### Site Header (`components/site-header.tsx`)
Navigation bar with theme toggle and user account options.

### Theme Context (`contexts/theme-context.tsx`)
Manages application-wide dark/light theme switching.

### Geolocation Hook (`hooks/use-geolocation.ts`)
Custom hook for browser geolocation API integration.

---

## 🔒 Security Features

- ✅ Protected routes for authenticated users
- ✅ Environment variable encryption for API keys
- ✅ Input validation with Zod schema validation
- ✅ XSS protection through React's built-in sanitization
- ✅ CORS-safe API route handling
- ✅ Secure authentication flow

---

## 📱 Responsive Breakpoints

| Breakpoint | Screen Size | Optimizations |
|-----------|------------|--------------|
| Mobile | < 640px | Single column, Touch-friendly buttons, Simplified map |
| Tablet | 640px - 1024px | Two columns, Balanced spacing |
| Desktop | > 1024px | Three columns, Full map sidebar, Advanced features |

---

## 🎯 Performance Optimizations

- **Lazy Loading**: Components load on demand
- **Image Optimization**: Next.js Image component for responsive images
- **Smart Caching**: Prevents redundant API calls
- **Code Splitting**: Route-based code splitting with Next.js
- **CSS-in-JS**: Tailwind CSS for minimal CSS bundle
- **Compression**: Gzip compression enabled by default

---

## 🚧 Future Enhancements

- [ ] User favorites/bookmarks system
- [ ] Social sharing functionality
- [ ] Place ratings and reviews
- [ ] Personalized recommendations
- [ ] Offline mode with PWA support
- [ ] Advanced filters (price range, hours, amenities)
- [ ] Event calendar integration
- [ ] Real-time availability status

---

## 📝 License

This project is proprietary software created by Viraj Sawant. All rights reserved.

---

## 👨‍💻 Creator

**Viraj Sawant**

- 🌐 Portfolio: [https://virajr7123-portfolio-me.netlify.app/]
- 📧 Email: [sawantviraj976@gmail.com]
- 🐙 GitHub: [https://github.com/Virajr7123]

---

## 📞 Support

For issues, questions, or feature requests, please:
1. Check existing GitHub issues
2. Create a detailed bug report or feature request
3. Contact the creator directly

---

## 🙏 Acknowledgments

- **Next.js Team** - For the amazing React framework
- **Tailwind CSS** - For utility-first CSS
- **shadcn/ui** - For the beautiful component library
- **Foursquare** - For place data and API
- **Google** - For maps and photos API
- **Lucide** - For beautiful icons
- **The Open Source Community** - For countless libraries and tools

---

<div align="center">

**Made with 🌿 by [Viraj Sawant](https://github.com/Virajr7123)**

⭐ Star this repository if you find it helpful!

</div>
