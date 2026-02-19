# Deep Dive: Your-mnee-space

## README Summary
# YourSpace Creative Labs

> **A next-generation creative platform powered by Supervisor AI** — connecting artists, mentors, and learners through intelligent virtual spaces, autonomous agent workflows, and real-time collaboration.

**Live Platform:** [https://tqpwalgy7lt2.space.minimax.io](https://tqpwalgy7lt2.space.minimax.io)
**GitHub Repository:** [https://github.com/12Matt3r/Your-mnee-space](https://github.com/12Matt3r/Your-mnee-space)

---

## Table of Contents

1. [What is YourSpace?](#what-is-yourspace)
2. [Supervisor AI — The Core Intelligence](#supervisor-ai--the-core-intelligence)
3. [Platform Architecture](#platform-architecture)
4. [Features Deep Dive](#features-deep-dive)
5. [Technical Implementation](#technical-implementation)
6. [Database Schema](#database-schema)
7. [API & Edge Functions](#api--edge-functions)
8. [Roadmap & Future Vision](#roadmap--future-vision)
9. [Getting Started](#getting-started)
10. [License](#license)

---

## What is YourSpace?

YourSpace is a **creator-first social platform** that combines:

- **Immersive Virtual Rooms** — Customizable 2D/3D spaces where creators can express their brand, interact with fans, and host events.
- **AI-Powered Workflows** — Autonomous agents that handle content moderation, audience engagement, analytics, and creative assistance.
- **Economic Infrastructure** — Integrated payments, tipping, and token-based incentives via MNEE/Stripe.
- **Real-Time Collaboration** — Live streaming, screen sharing, and collaborative creation sessions.

### Why Does YourSpace Exist?

Traditional social platforms treat creators as content generators for ad revenue. YourSpace flips this model:

| Traditional Platforms | YourSpace |
|-----------------------|-----------|
| Algorithm controls visibility | Creator controls their space |
| Platform takes 30-50% cut | Direct creator-to-fan economics |
| One-size-fits-all profiles | Fully customizable virtual rooms |
| Manual everything | AI agents automate repetitive tasks |

### When Should You Use YourSpace?

- **Artists & Musicians** — Build an immersive space that represents your aesthetic, go live on Discord, and let AI agents engage your audience while you focus on creating.
- **Educators & Mentors** — Host virtual classes, manage student progress with AI assistance, and monetize your expertise.
- **Communities** — Create shared spaces with arcades, galleries, and lounges where members can interact in real-time.


## Project Structure
```
temp_repos/Your-mnee-space
temp_repos/Your-mnee-space/pnpm-lock.yaml
temp_repos/Your-mnee-space/vitest.config.ts
temp_repos/Your-mnee-space/index.html
temp_repos/Your-mnee-space/vite.config.ts
temp_repos/Your-mnee-space/README.md
temp_repos/Your-mnee-space/components.json
temp_repos/Your-mnee-space/transform_videos.js
temp_repos/Your-mnee-space/supabase
temp_repos/Your-mnee-space/supabase/functions
temp_repos/Your-mnee-space/supabase/migrations
temp_repos/Your-mnee-space/supabase/tables
temp_repos/Your-mnee-space/supabase/computer_assets_setup.sql
temp_repos/Your-mnee-space/eslint.config.js
temp_repos/Your-mnee-space/postcss.config.js
temp_repos/Your-mnee-space/package-lock.json
temp_repos/Your-mnee-space/tsconfig.app.json
temp_repos/Your-mnee-space/tailwind.config.js
temp_repos/Your-mnee-space/package.json
temp_repos/Your-mnee-space/ROADMAP.md
temp_repos/Your-mnee-space/api
temp_repos/Your-mnee-space/api/ai-tasks.ts
temp_repos/Your-mnee-space/POLLINATIONS_SETUP.md
temp_repos/Your-mnee-space/PHASE_1_COMPLETION_REPORT.md
temp_repos/Your-mnee-space/tsconfig.node.json
temp_repos/Your-mnee-space/LICENSE
temp_repos/Your-mnee-space/public
temp_repos/Your-mnee-space/public/data
temp_repos/Your-mnee-space/public/images
temp_repos/Your-mnee-space/public/use.txt
temp_repos/Your-mnee-space/COMPUTER_INTEGRATION_COMPLETE.md
temp_repos/Your-mnee-space/AI_SERVICES_SETUP.md
temp_repos/Your-mnee-space/tailwind.config.ts
temp_repos/Your-mnee-space/PITCH.md
temp_repos/Your-mnee-space/ARCHITECTURE.md
temp_repos/Your-mnee-space/src
temp_repos/Your-mnee-space/src/data
temp_repos/Your-mnee-space/src/App.tsx
temp_repos/Your-mnee-space/src/App.css
temp_repos/Your-mnee-space/src/test
temp_repos/Your-mnee-space/src/hooks
temp_repos/Your-mnee-space/src/components
temp_repos/Your-mnee-space/src/assets
temp_repos/Your-mnee-space/src/types
temp_repos/Your-mnee-space/src/contexts
temp_repos/Your-mnee-space/src/index.css
temp_repos/Your-mnee-space/src/vite-env.d.ts
temp_repos/Your-mnee-space/src/lib
temp_repos/Your-mnee-space/src/main.tsx
temp_repos/Your-mnee-space/src/pages
temp_repos/Your-mnee-space/videos_data.json
temp_repos/Your-mnee-space/tsconfig.json
```

## Tech Stack (package.json)
```json
{
  "name": "react_repo",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "yes | pnpm install && vite",
    "build": "yes | pnpm install && rm -rf node_modules/.vite-temp && vite build",
    "build:prod": "yes | pnpm install && rm -rf node_modules/.vite-temp && tsc -b && BUILD_MODE=prod vite build",
    "lint": "yes | pnpm install && eslint .",
    "preview": "yes | pnpm install && vite preview",
    "test": "vitest run",
    "test:watch": "vitest"
  },
  "dependencies": {
    "@babel/types": "^7.26.10",
    "@dnd-kit/core": "^6.3.1",
    "@dnd-kit/sortable": "^10.0.0",
    "@dnd-kit/utilities": "^3.2.2",
    "@headlessui/react": "^2.2.7",
    "@heroicons/react": "^2.2.0",
    "@hookform/resolvers": "^3.10.0",
    "@mnee/ts-sdk": "^1.0.3",
    "@monaco-editor/react": "^4.7.0",
    "@radix-ui/react-accordion": "^1.2.2",
    "@radix-ui/react-alert-dialog": "^1.1.4",
    "@radix-ui/react-aspect-ratio": "^1.1.1",
    "@radix-ui/react-avatar": "^1.1.2",
    "@radix-ui/react-checkbox": "^1.1.3",
    "@radix-ui/react-collapsible": "^1.1.2",
    "@radix-ui/react-context-menu": "^2.2.4",
    "@radix-ui/react-dialog": "^1.1.4",
    "@radix-ui/react-dropdown-menu": "^2.1.4",
    "@radix-ui/react-hover-card": "^1.1.4",
    "@radix-ui/react-label": "^2.1.1",
    "@radix-ui/react-menubar": "^1.1.4",
    "@radix-ui/react-navigation-menu": "^1.2.3",
    "@radix-ui/react-popover": "^1.1.4",
    "@radix-ui/react-progress": "^1.1.1",
    "@radix-ui/react-radio-group": "^1.2.2",
    "@radix-ui/react-scroll-area": "^1.2.2",
    "@radix-ui/react-select": "^2.1.4",
    "@radix-ui/react-separator": "^1.1.1",
    "@radix-ui/react-slider": "^1.2.2",
    "@radix-ui/react-slot": "^1.1.1",
    "@radix-ui/react-switch": "^1.1.2",
    "@radix-ui/react-tabs": "^1.1.2",
    "@radix-ui/react-toast": "^1.2.4",
    "@radix-ui/react-toggle": "^1.1.1",
    "@radix-ui/react-toggle-group": "^1.1.1",
    "@radix-ui/react-tooltip": "^1.1.6",
    "@react-three/cannon": "^6.6.0",
    "@react-three/drei": "^9.112.0",
    "@react-three/fiber": "^8.17.10",
    "@stripe/react-stripe-js": "^3.9.0",
    "@stripe/stripe-js": "^7.8.0",
    "@supabase/supabase-js": "^2.55.0",
    "@tanstack/react-query": "^5.85.3",
    "@types/three": "^0.166.0",
    "canvas-confetti": "^1.9.3",
    "class-variance-authority": "^0.7.1",
    "clsx": "^2.1.1",
    "cmdk": "1.0.0",
    "date-fns": "^3.0.0",
    "embla-carousel-react": "^8.5.2",
    "framer-motion": "^12.23.12",
    "input-otp": "^1.4.2",
    "lucide-react": "^0.364.0",
    "next-themes": "^0.4.4",
    "react": "^18.3.1",
    "react-audio-player": "^0.17.0",
    "react-day-picker": "8.10.1",
    "react-dom": "^18.3.1",
    "react-dropzone": "^14.3.8",
    "react-grid-layout": "^1.5.2",
    "react-hook-form": "^7.54.2",
    "react-hot-toast": "^2.5.2",
    "react-intersection-observer": "^9.16.0",
    "react-query": "^3.39.3",
    "react-resizable-panels": "^2.1.7",
    "react-router-dom": "^6",
    "react-spring": "^10.0.1",
    "recharts": "^2.12.4",
    "sonner": "^1.7.2",
    "sound-manager": "^0.19.5",
    "tailwind-merge": "^2.6.0",
    "tailwindcss-animate": "^1.0.7",
    "three": "^0.166.1",
    "vaul": "^1.1.2",
    "viem": "^2.44.1",
    "wagmi": "^3.3.1",
    "wavesurfer.js": "^7.10.1",
    "zod": "^3.24.1"
  },
  "devDependencies": {
    "@eslint/js": "^9.15.0",
    "@testing-library/jest-dom": "^6.9.1",
    "@testing-library/react": "^16.3.1",
    "@testing-library/user-event": "^14.6.1",
    "@types/node": "^22.10.7",
    "@types/react": "^18.3.12",
    "@types/react-dom": "^18.3.1",
    "@types/react-router-dom": "^5",
    "@vitejs/plugin-react": "^4.3.4",
    "autoprefixer": "10.4.20",
    "eslint": "^9.15.0",
    "eslint-plugin-react-hooks": "^5.0.0",
    "eslint-plugin-react-refresh": "^0.4.14",
    "globals": "^15.12.0",
    "jsdom": "^27.4.0",
    "playwright": "^1.57.0",
    "postcss": "8.4.49",
    "tailwindcss": "v3.4.16",
    "typescript": "~5.6.2",
    "typescript-eslint": "^8.15.0",
    "vite": "^6.0.1",
    "vite-plugin-source-info": "^1.0.0",
    "vitest": "^4.0.16"
  }
}
```


## Unique Code Findings

### 🤖 AI Agent System (src/hooks/useAIAgents.ts)
- **Autonomous Economics**: Implements a complete "Hire Agent" workflow where users (or other agents) can post jobs with MNEE budgets.
- **Service Fallback**: Cleverly rotates between free AI providers (MiniMax Lightning, Groq, Pollinations) to ensure zero-cost, high-availability AI tasks.
- **Verification Loop**: Includes a `verifyTask` function that can programmatically score and validate the output of an agent against criteria.

### 👩‍💻 Jules AI Integration (src/hooks/useJulesAI.ts)
- **Integrated Assistant**: A specialized hook for a resident AI named Jules (referenced in the credits of Supervisorai).
- **Capabilities**:
  - `generateCode`: Language-aware code generation.
  - `debugCode`: Fixes bugs based on error messages.
  - `refactorCode`: Improves code quality based on specific goals.
  - `writeFunction`: High-level abstraction for generating boilerplate-free functions.

### 🎵 Audio Engine (src/components/music/AudioEngine.ts)
- **Multi-Source**: Supports traditional audio files and YouTube-based audio streams.
- **Global Sync**: Uses a `GlobalMusicProvider` to maintain audio state across page transitions.

### 🎮 Arcade Module (src/components/room/Arcade.tsx)
- **Embedded Games**: Features a collection of Three.js based mini-games like "Void Runner" and "NFT Quest" playable within the 3D room environment.
