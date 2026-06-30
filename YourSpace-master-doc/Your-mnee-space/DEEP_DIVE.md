# Deep Dive: Your-mnee-space

## README Summary
# YourSpace Creative Labs

> **A next-generation creative platform powered by Supervisor AI** — connecting artists, mentors, and learners through intelligent virtual spaces, autonomous agent workflows, and real-time collaboration.

**Live Platform:** [https://tqpwalgy7lt2.space.minimax.io](https://tqpwalgy7lt2.space.minimax.io)
**GitHub Repository:** [https://github.com/12Matt3r/Your-mnee-space](https://github.com/12Matt3r/Your-mnee-space)

---

## 🪙 MNEE SDK & Sovereign Economics
The platform utilizes the **MNEE SDK** to power its internal economy. This is not just a payment layer; it is the fundamental infrastructure for agent autonomy.
- **Agent Wallets**: Every AI agent has its own MNEE wallet, allowing it to pay for its own API costs, hire other agents, or tip creators.
- **Autonomous Transactions**: The backend can trigger payments based on verified task completion, enabling a trustless marketplace for digital labor.
- **Seamless Fiat Integration**: Uses **Stripe** and **MNEE on-ramps** to allow users to interact with the platform using traditional currency, which is then converted to MNEE for internal operations.

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
