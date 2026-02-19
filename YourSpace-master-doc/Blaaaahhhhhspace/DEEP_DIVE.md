# Deep Dive: Blaaaahhhhhspace

## README Summary
# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type aware lint rules:

- Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

- Replace `tseslint.configs.recommended` to `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
- Optionally add `...tseslint.configs.stylisticTypeChecked`
- Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'

export default tseslint.config({
  // Set the react version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```

## Project Structure
```
temp_repos/Blaaaahhhhhspace
temp_repos/Blaaaahhhhhspace/pnpm-lock.yaml
temp_repos/Blaaaahhhhhspace/vitest.config.ts
temp_repos/Blaaaahhhhhspace/index.html
temp_repos/Blaaaahhhhhspace/vitest.config.extended.ts
temp_repos/Blaaaahhhhhspace/vite.config.ts
temp_repos/Blaaaahhhhhspace/README.md
temp_repos/Blaaaahhhhhspace/components.json
temp_repos/Blaaaahhhhhspace/supabase
temp_repos/Blaaaahhhhhspace/supabase/functions
temp_repos/Blaaaahhhhhspace/supabase/tables
temp_repos/Blaaaahhhhhspace/supabase/computer_assets_setup.sql
temp_repos/Blaaaahhhhhspace/eslint.config.js
temp_repos/Blaaaahhhhhspace/TESTING.docx
temp_repos/Blaaaahhhhhspace/postcss.config.js
temp_repos/Blaaaahhhhhspace/tests
temp_repos/Blaaaahhhhhspace/tests/README.md
temp_repos/Blaaaahhhhhspace/tests/e2e
temp_repos/Blaaaahhhhhspace/tests/helpers
temp_repos/Blaaaahhhhhspace/tests/fixtures
temp_repos/Blaaaahhhhhspace/tests/setup-extended.ts
temp_repos/Blaaaahhhhhspace/tests/unit
temp_repos/Blaaaahhhhhspace/tsconfig.app.json
temp_repos/Blaaaahhhhhspace/tailwind.config.js
temp_repos/Blaaaahhhhhspace/TESTING.pdf
temp_repos/Blaaaahhhhhspace/package.json
temp_repos/Blaaaahhhhhspace/TESTING.md
temp_repos/Blaaaahhhhhspace/PHASE_1_COMPLETION_REPORT.md
temp_repos/Blaaaahhhhhspace/tsconfig.node.json
temp_repos/Blaaaahhhhhspace/public
temp_repos/Blaaaahhhhhspace/public/data
temp_repos/Blaaaahhhhhspace/public/images
temp_repos/Blaaaahhhhhspace/public/use.txt
temp_repos/Blaaaahhhhhspace/playwright.config.ts
temp_repos/Blaaaahhhhhspace/COMPUTER_INTEGRATION_COMPLETE.md
temp_repos/Blaaaahhhhhspace/tailwind.config.ts
temp_repos/Blaaaahhhhhspace/ARCHITECTURE.md
temp_repos/Blaaaahhhhhspace/src
temp_repos/Blaaaahhhhhspace/src/App.tsx
temp_repos/Blaaaahhhhhspace/src/App.css
temp_repos/Blaaaahhhhhspace/src/hooks
temp_repos/Blaaaahhhhhspace/src/components
temp_repos/Blaaaahhhhhspace/src/assets
temp_repos/Blaaaahhhhhspace/src/types
temp_repos/Blaaaahhhhhspace/src/__tests__
temp_repos/Blaaaahhhhhspace/src/contexts
temp_repos/Blaaaahhhhhspace/src/index.css
temp_repos/Blaaaahhhhhspace/src/vite-env.d.ts
temp_repos/Blaaaahhhhhspace/src/lib
temp_repos/Blaaaahhhhhspace/src/main.tsx
temp_repos/Blaaaahhhhhspace/src/pages
temp_repos/Blaaaahhhhhspace/tsconfig.json
```

## Tech Stack (package.json)
```json
{
  "name": "yourspace-creative-labs",
  "private": true,
  "version": "1.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc -b && vite build",
    "lint": "eslint .",
    "preview": "vite preview",
    "test": "vitest",
    "test:ui": "vitest --ui",
    "test:run": "vitest run",
    "test:coverage": "vitest run --coverage",
    "test:watch": "vitest --watch",
    "e2e": "playwright test",
    "e2e:ui": "playwright test --ui",
    "e2e:headed": "playwright test --headed",
    "test:all": "npm run test:run && npm run e2e"
  },
  "dependencies": {
    "@radix-ui/react-dialog": "^1.1.1",
    "@radix-ui/react-dropdown-menu": "^2.1.1",
    "@radix-ui/react-label": "^2.1.0",
    "@radix-ui/react-select": "^2.1.1",
    "@radix-ui/react-separator": "^1.1.0",
    "@radix-ui/react-slider": "^1.2.0",
    "@radix-ui/react-slot": "^1.1.0",
    "@radix-ui/react-switch": "^1.1.0",
    "@radix-ui/react-tabs": "^1.1.0",
    "@radix-ui/react-toast": "^1.2.1",
    "@react-three/drei": "^9.114.0",
    "@react-three/fiber": "^8.17.10",
    "@supabase/supabase-js": "^2.46.1",
    "@stripe/stripe-js": "^4.7.0",
    "class-variance-authority": "^0.7.0",
    "clsx": "^2.1.1",
    "framer-motion": "^11.11.1",
    "lucide-react": "^0.447.0",
    "react": "^18.3.1",
    "react-dnd": "^16.0.1",
    "react-dnd-html5-backend": "^16.0.1",
    "react-dom": "^18.3.1",
    "react-grid-layout": "^1.4.4",
    "react-router-dom": "^6.28.0",
    "tailwind-merge": "^2.5.3",
    "tailwindcss-animate": "^1.0.7",
    "three": "^0.169.0",
    "zustand": "^5.0.0"
  },
  "devDependencies": {
    "@eslint/js": "^9.13.0",
    "@playwright/test": "^1.48.0",
    "@testing-library/jest-dom": "^6.6.3",
    "@testing-library/react": "^16.0.1",
    "@testing-library/user-event": "^14.5.2",
    "@types/node": "^22.8.6",
    "@types/react": "^18.3.12",
    "@types/react-dom": "^18.3.1",
    "@types/react-grid-layout": "^1.3.5",
    "@types/three": "^0.169.0",
    "@vitejs/plugin-react": "^4.3.3",
    "@vitest/coverage-v8": "^2.1.4",
    "@vitest/ui": "^2.1.4",
    "autoprefixer": "^10.4.20",
    "eslint": "^9.13.0",
    "eslint-plugin-react-hooks": "^5.0.0",
    "eslint-plugin-react-refresh": "^0.4.14",
    "globals": "^15.11.0",
    "jsdom": "^25.0.1",
    "postcss": "^8.4.47",
    "tailwindcss": "^3.4.14",
    "typescript": "~5.6.2",
    "typescript-eslint": "^8.10.0",
    "vite": "^5.4.10",
    "vitest": "^2.1.4"
  }
}```
