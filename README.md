# KISSAN AI

> **Smart Farming. Smarter Decisions. Better Harvests.**

An AI-Powered Multi-Crop Monitoring and Decision Support Platform for Farmers.

---

## Architecture Overview

- **Frontend (`apps/web`)**: React + Vite + TypeScript + Tailwind CSS, Radix UI primitives, React Router, TanStack Query, react-hook-form + zod, react-i18next.
- **Backend Platform**: Supabase (PostgreSQL, Auth with Phone OTP via Twilio Verify, Storage, Realtime, Edge Functions).
- **Computer Vision & ML Service (`services/vision-ml`)**: FastAPI on Google Cloud Run (OpenCV registration, scikit-image SSIM, scikit-learn).
- **AI Agricultural Assistant**: Google Gemini (called only from Supabase Edge Functions with caller-JWT authorization).
- **Weather Service**: Open-Meteo API (cached in `weather_cache`).

---

## Quick Start

1. **Install frontend dependencies**:
   ```bash
   cd apps/web
   npm install
   ```

2. **Start the web development server**:
   ```bash
   npm run dev
   ```
   Open [http://localhost:5173](http://localhost:5173) in your browser.
   To preview all design tokens and accessible UI components, open [http://localhost:5173/dev/design](http://localhost:5173/dev/design).

3. **Run unit tests & security audits**:
   ```bash
   npm run test          # Vitest unit test suite
   npm run check-secrets # Leaked secret scanner
   npm run build         # Production TypeScript build
   ```

For detailed setup instructions, please consult [`docs/SETUP.md`](docs/SETUP.md).
For the database schema and RLS policies, refer to [`docs/schema-reference.sql`](docs/schema-reference.sql).
