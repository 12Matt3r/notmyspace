# Deep Dive: yourbrokenspace

## Project Summary
`yourbrokenspace` serves as the **Intelligent Middleware** and **Flow Engine** for the YourSpace ecosystem. It is a specialized repository built to house and orchestrate high-level AI workflows using **Firebase Genkit**.

---

## 🧐 What is it?
It is a "Library of Intelligence"—a collection of modular, autonomous AI sub-agents (Flows) that handle specialized tasks within the YourSpace platform. While other repos handle the 3D rooms or the social feed, `yourbrokenspace` handles the "thinking" behind the creative features.

## 🎯 What does it do?
It implements approximately 17 specialized AI workflows, including:
- **DJ Commentary**: Generates professional, "cool" radio DJ scripts for YourSpace Radio.
- **Creative Quest Generator**: Analyzes user skills and interests to create personalized "missions" (e.g., "Write a 100-word sci-fi story").
- **Vibe Tagging**: Automatically classifies images, audio, and text by emotional "vibe" and community trends.
- **Mentorship & Learning**: Generates custom learning paths and provides real-time coaching for aspiring creators.
- **Content Enhancement**: Includes flows for image refinement, lyrics generation, and portfolio assembly.

## 💡 Why does it do it?
The goal is to provide **Context-Aware Assistance**. Instead of generic AI, `yourbrokenspace` creates agents that "know" the user. For example, the Quest Generator doesn't just give a random task; it looks at what the user has recently created and what skills they want to improve, making the platform feel like a true creative partner.

## 🛠️ How does it do it? (Technical Implementation)
- **Firebase Genkit**: The core framework used to define, test, and deploy AI flows.
- **Google Gemini 2.0 Flash**: The primary LLM, chosen for its speed and multi-modal capabilities.
- **Zod Validation**: Every flow has strictly defined input and output schemas, ensuring the AI never returns "broken" data to the frontend.
- **Server Actions**: Implemented with `'use server'` for seamless integration into React/Next.js frontends while maintaining security.
- **Structured Prompting**: Uses Handlebars templates to inject complex data (like arrays of user skills) into prompts dynamically.

## 🚀 The Future Vision
Based on the current architecture, the roadmap for `yourbrokenspace` includes:
1.  **Autonomous Agent Hiring**: Integrating with the MNEE economy so these flows can be "hired" as independent agents.
2.  **Meta-Flows**: Supervisor AI using these flows as "tools" to solve higher-level platform problems.
3.  **Real-Time Multi-modal Search**: Building a discovery engine that understands the "vibe" of assets as deeply as a human curator.
4.  **Persistent AI Memory**: Allowing the Mentor AI to remember a user's progress across months of creative work.

## ✅ Current Implementation Status (What's Live)
- **17 Functional Flows**: The core logic for DJing, Mentoring, Quests, and Vibe Tagging is complete.
- **Genkit Integration**: The environment is fully configured for Google AI and Gemini 2.0.
- **Personalized Logic**: Systems for injecting user data into AI prompts are implemented and tested.
- **Mock Integration**: Includes test suites and mock data to verify flow behavior.

---

## Project Structure
```
temp_repos/yourbrokenspace
temp_repos/yourbrokenspace/vitest.config.ts
temp_repos/yourbrokenspace/pnpm-lock.yaml
temp_repos/yourbrokenspace/package.json
temp_repos/yourbrokenspace/package-lock.json
temp_repos/yourbrokenspace/test
temp_repos/yourbrokenspace/lib
temp_repos/yourbrokenspace/hooks
temp_repos/yourbrokenspace/app
temp_repos/yourbrokenspace/contexts
temp_repos/yourbrokenspace/ai
temp_repos/yourbrokenspace/ai/genkit.ts
temp_repos/yourbrokenspace/ai/dev.ts
temp_repos/yourbrokenspace/ai/flows
temp_repos/yourbrokenspace/config
temp_repos/yourbrokenspace/components
```

## Tech Stack (package.json)
```json
{
  "scripts": {
    "test": "node_modules/.bin/vitest",
    "test:watch": "node_modules/.bin/vitest --watch",
    "test:ci": "node_modules/.bin/vitest run --coverage"
  },
  "dependencies": {
    "react": "^19.1.1",
    "react-dom": "^19.1.1",
    "zod": "^4.1.5"
  },
  "devDependencies": {
    "@testing-library/jest-dom": "^6.8.0",
    "@testing-library/react": "^16.3.0",
    "@testing-library/user-event": "^14.6.1",
    "@vitest/coverage-v8": "^3.2.4",
    "jsdom": "^26.1.0",
    "vitest": "^3.2.4",
    "whatwg-url": "^14.2.0"
  }
}
```
