# Deep Dive: yourbrokenspace

## 🎭 Specialized AI Flows
This module contains the library of "Flows"—autonomous, specialized AI workflows designed for specific creative tasks.
- **Lyric Studio & Lyrics Generator**: (Confirmed in `app/lyric-studio`) — Tools for generating song lyrics based on genre, mood, and "vibe" parameters.
- **DJ Commentary**: Generates real-time, vibe-aware commentary to accompany music streams, enhancing the "live" feel of automated broadcasts.
- **Quest Generator**: (Confirmed in `app/arcade`) — Creates interactive, narrative-driven quests for the platform's virtual room arcades.
- **Vibe Tagging**: (Confirmed in `app/vibe-tagging`) — Uses multi-modal analysis to automatically tag content with emotional and aesthetic "vibes".

## Project Structure
```
temp_repos/yourbrokenspace
temp_repos/yourbrokenspace/pnpm-lock.yaml
temp_repos/yourbrokenspace/vitest.config.ts
temp_repos/yourbrokenspace/config
temp_repos/yourbrokenspace/config/notificationsData.ts
temp_repos/yourbrokenspace/config/walkthroughChannels.ts
temp_repos/yourbrokenspace/config/games.ts
temp_repos/yourbrokenspace/config/earningsData.ts
temp_repos/yourbrokenspace/config/eventsData.ts
temp_repos/yourbrokenspace/config/fanInvestmentData.ts
temp_repos/yourbrokenspace/config/guildData.ts
temp_repos/yourbrokenspace/config/profileData.ts
temp_repos/yourbrokenspace/config/challengeData.ts
temp_repos/yourbrokenspace/config/dashboardData.ts
temp_repos/yourbrokenspace/config/messagingData.ts
temp_repos/yourbrokenspace/test
temp_repos/yourbrokenspace/test/setupTests.ts
temp_repos/yourbrokenspace/hooks
temp_repos/yourbrokenspace/hooks/use-toast.ts
temp_repos/yourbrokenspace/hooks/use-mobile.tsx
temp_repos/yourbrokenspace/components
temp_repos/yourbrokenspace/components/ThemeSwitcher.tsx
temp_repos/yourbrokenspace/components/layout
temp_repos/yourbrokenspace/components/PageWrapper.tsx
temp_repos/yourbrokenspace/components/theme-toggle.tsx
temp_repos/yourbrokenspace/components/feature
temp_repos/yourbrokenspace/components/branding
temp_repos/yourbrokenspace/components/ui
temp_repos/yourbrokenspace/package-lock.json
temp_repos/yourbrokenspace/contexts
temp_repos/yourbrokenspace/contexts/MentorAIContext.tsx
temp_repos/yourbrokenspace/contexts/UserContext.tsx
temp_repos/yourbrokenspace/contexts/WhisperNetContext.tsx
temp_repos/yourbrokenspace/ai
temp_repos/yourbrokenspace/ai/genkit.ts
temp_repos/yourbrokenspace/ai/dev.ts
temp_repos/yourbrokenspace/ai/flows
temp_repos/yourbrokenspace/package.json
temp_repos/yourbrokenspace/lib
temp_repos/yourbrokenspace/lib/firebase
temp_repos/yourbrokenspace/lib/theme
temp_repos/yourbrokenspace/lib/actions
temp_repos/yourbrokenspace/lib/utils.ts
temp_repos/yourbrokenspace/app
temp_repos/yourbrokenspace/app/portfolio-generator
temp_repos/yourbrokenspace/app/walkthrough
temp_repos/yourbrokenspace/app/layout.tsx
temp_repos/yourbrokenspace/app/challenges
temp_repos/yourbrokenspace/app/terms
temp_repos/yourbrokenspace/app/about-us
temp_repos/yourbrokenspace/app/privacy
temp_repos/yourbrokenspace/app/signup
temp_repos/yourbrokenspace/app/lyric-studio
temp_repos/yourbrokenspace/app/radio
temp_repos/yourbrokenspace/app/earnings
temp_repos/yourbrokenspace/app/auth
temp_repos/yourbrokenspace/app/page.tsx
temp_repos/yourbrokenspace/app/login
temp_repos/yourbrokenspace/app/guilds
temp_repos/yourbrokenspace/app/following
temp_repos/yourbrokenspace/app/events
temp_repos/yourbrokenspace/app/creations
temp_repos/yourbrokenspace/app/stream-settings
temp_repos/yourbrokenspace/app/upload
temp_repos/yourbrokenspace/app/explore
temp_repos/yourbrokenspace/app/collaborate
temp_repos/yourbrokenspace/app/creators
temp_repos/yourbrokenspace/app/content-refinement
temp_repos/yourbrokenspace/app/providers.tsx
temp_repos/yourbrokenspace/app/fan-investments
temp_repos/yourbrokenspace/app/learning
temp_repos/yourbrokenspace/app/image-generator
temp_repos/yourbrokenspace/app/image-enhancer
temp_repos/yourbrokenspace/app/about
temp_repos/yourbrokenspace/app/canvas
temp_repos/yourbrokenspace/app/globals.css
temp_repos/yourbrokenspace/app/dashboard
temp_repos/yourbrokenspace/app/vibe-tagging
temp_repos/yourbrokenspace/app/favicon.ico
temp_repos/yourbrokenspace/app/lyrics-generator
temp_repos/yourbrokenspace/app/whisper-net
temp_repos/yourbrokenspace/app/profile
temp_repos/yourbrokenspace/app/arcade
temp_repos/yourbrokenspace/app/subscriptions
temp_repos/yourbrokenspace/app/notifications
temp_repos/yourbrokenspace/app/event-planner
```
