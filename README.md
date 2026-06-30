<div align="center">

<h1>Safar360</h1>

<p>Safar360 is an AI-powered travel companion built for explorers who want more than the usual tourist trail.<br/>It blends intelligent trip planning, immersive 360° experiences, and real-time tools into one platform — making it easier to discover, plan, and experience travel across India and the world.</p>

[![React](https://img.shields.io/badge/React-18.3-61DAFB?style=flat-square&logo=react&logoColor=white)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-5.x-646CFF?style=flat-square&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-3.x-38BDF8?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)](https://supabase.com/)
[![Clerk](https://img.shields.io/badge/Clerk-6C47FF?style=flat-square&logo=clerk&logoColor=white)](https://clerk.com/)
[![License](https://img.shields.io/badge/License-MIT-gray?style=flat-square)](LICENSE)

**[Live Demo](https://safar360.vercel.app)** &nbsp;·&nbsp; [Report Bug](https://github.com/Rahul04-alt/Safar360/issues) &nbsp;·&nbsp; [Request Feature](https://github.com/Rahul04-alt/Safar360/issues)

</div>

---

## About

Safar360 redefines how people discover and experience travel by combining AI-generated itineraries, immersive 360° VR tours, real-time interactive maps, and a social travel community into a single platform. It surfaces India's lesser-known destinations alongside global travel planning — helping users go beyond the obvious and explore with confidence.

---

## Features

**AI & Planning**
- **AI Itinerary Planner** — Google Gemini-powered day-by-day trip plans with seasonal, budget, and state-aware context
- **SafarX AI Agent** — Conversational AI agent for flight search, hotel discovery, web search via Tavily, and automated trip planning
- **Trip Confidence Meter** — Pre-trip checklist with an animated readiness score based on completion

**Exploration & Discovery**
- **Interactive 3D Globe** — WebGL Earth rendered with React Three Fiber and a procedural star field
- **360° VR Tours** — Panoramic viewer with WebXR support across 50+ global destinations
- **Hidden Gems** — Curated off-beat Indian destinations with filters by state, type, and best season
- **Google Earth Explorer** — Embedded satellite and street-level exploration within the app
- **Interactive Maps** — Leaflet-based destination explorer with OSRM routing and live distance calculation

**Bookings & Tracking**
- **Flight Search & Booking** — Real-time flight search and booking via TBO API through SafarX Agent
- **Hotel Discovery & Booking** — Live hotel listings, details, and booking via TripAdvisor / RapidAPI
- **Live Flight Tracker** — Real-time flight status and global route visualization via AviationStack

**Community & Social**
- **Social Travel Groups** — Create or join travel communities, coordinate meetups, find compatible travel partners
- **Travel Matchmaker** — Match with other users based on destination preferences and travel style
- **Group Events & Discussions** — In-group event planning, photo sharing, and discussion threads

**Utilities**
- **Document Vault** — Secure storage for travel documents (passport, visa, tickets) backed by Supabase Storage
- **Media Upload** — Community photo contributions with Cloudinary-backed storage
- **Ambient Music Player** — Background music and ambient sounds for the exploration experience
- **PWA Support** — Installable app with offline caching via service worker

---

## Tech Stack

**Frontend**
- React 18 + Vite 5
- Tailwind CSS + Framer Motion
- React Three Fiber + @react-three/drei (3D globe)
- Leaflet + React Leaflet (maps)
- React Query + Axios (data fetching)
- Clerk (authentication)

**Backend & Services**
- Node.js + Express — document vault API (hosted on Render)
- Supabase — PostgreSQL database + file storage
- MongoDB Atlas — document metadata
- Google Gemini Pro — AI itinerary and chat generation
- A-Frame + WebXR — 360° VR rendering
- Cloudinary — media storage and delivery

**External APIs**
- TBO API — flight search and booking
- TripAdvisor via RapidAPI — hotel listings and details
- Tavily — AI-assisted travel web search
- AviationStack — live flight tracking
- OpenWeather — weather-based trip confidence scoring
- OSRM — open-source route distance calculation
- Flickr — destination photo discovery
- Google Maps — destination coordinates and place search
- Hugging Face Spaces — SafarX AI agent backend

---

## Project Structure

```
Safar360/
├── public/               # Static assets, PWA manifest, service worker
├── server/               # Express backend for Document Vault
│   ├── middleware/       # JWT auth middleware
│   ├── models/           # Mongoose Document schema
│   └── routes/           # /api/documents CRUD routes
└── src/
    ├── assets/           # Destination images (AVIF/WebP/JPEG)
    ├── components/
    │   ├── 3d/           # Globe and 3D scene (React Three Fiber)
    │   ├── animations/   # Aurora, ChromaGrid, ElectricBorder, MagicBento
    │   ├── SocialGroups/ # Groups, meetups, matchmaking UI
    │   └── VirtualTour/  # VR scene and panorama viewer
    ├── contexts/         # AppContext — global state
    ├── data/             # Static JSON (destinations, hidden gems, VR tours)
    ├── hooks/            # useApi, useAuth, useSearch, social hooks
    ├── lib/              # Supabase client
    ├── pages/
    │   └── AgentPage/    # SafarX AI agent (flights + hotels)
    ├── services/         # Gemini, API clients, recommendation engine
    └── utils/            # Constants, helpers, itinerary calculator
```

---

## Getting Started

### Prerequisites

- Node.js v20+
- Accounts: Supabase, Clerk, Cloudinary, MongoDB Atlas
- API keys: Google Gemini, AviationStack, OpenWeather, Flickr, Google Maps, RapidAPI, TBO, Tavily

### Installation

```bash
git clone https://github.com/Rahul04-alt/Safar360.git
cd Safar360
npm install
cd server && npm install && cd ..
```

### Environment Variables

Create **`.env.local`** in the project root:

```env
VITE_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
VITE_GEMINI_API_KEY=your_google_gemini_api_key
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key
VITE_SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key
VITE_API_BASE_URL=http://localhost:5000
VITE_AI_API_URL=http://localhost:8000
VITE_API_URL=https://bharatverse11-safarx.hf.space
VITE_CLOUD_NAME=your_cloudinary_cloud_name
VITE_CLOUD_API_KEY=your_cloudinary_api_key
VITE_GOOGLE_MAPS_KEY=your_google_maps_api_key
VITE_AVIATION_STACK_API_KEY=your_aviationstack_api_key
VITE_OPENWEATHER_API_KEY=your_openweather_api_key
VITE_FLICKR_API_KEY=your_flickr_api_key
```

Create **`server/.env`**:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
CLERK_SECRET_KEY=your_clerk_secret_key
CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret
```

### Running Locally

```bash
# Frontend — http://localhost:3000
npm run dev

# Backend (separate terminal)
cd server && node server.js
```

| Script | Description |
|---|---|
| `npm run dev` | Start Vite dev server |
| `npm run build` | Production build |
| `npm run preview` | Preview production build |
| `npm run lint` | Run ESLint |

---

## Deployment

| | Platform |
|---|---|
| Frontend | [Vercel](https://vercel.com/) |
| Backend | [Render](https://render.com/) |
| AI Agent | [Hugging Face Spaces](https://huggingface.co/spaces) |
| Database | [Supabase](https://supabase.com/) + [MongoDB Atlas](https://www.mongodb.com/atlas) |

---

## License

MIT

---

<div align="center">
<sub>Built for <strong>VOYAGEHACK 3.0</strong></sub>
</div>

