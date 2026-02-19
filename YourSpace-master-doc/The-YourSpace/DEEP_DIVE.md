# Deep Dive: The-YourSpace

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
temp_repos/The-YourSpace
temp_repos/The-YourSpace/index.html
temp_repos/The-YourSpace/vite.config.ts
temp_repos/The-YourSpace/README.md
temp_repos/The-YourSpace/components.json
temp_repos/The-YourSpace/supabase
temp_repos/The-YourSpace/supabase/functions
temp_repos/The-YourSpace/eslint.config.js
temp_repos/The-YourSpace/postcss.config.js
temp_repos/The-YourSpace/tsconfig.app.json
temp_repos/The-YourSpace/tailwind.config.js
temp_repos/The-YourSpace/package.json
temp_repos/The-YourSpace/tsconfig.node.json
temp_repos/The-YourSpace/public
temp_repos/The-YourSpace/public/use.txt
temp_repos/The-YourSpace/--store-dir
temp_repos/The-YourSpace/src
temp_repos/The-YourSpace/src/App.tsx
temp_repos/The-YourSpace/src/App.css
temp_repos/The-YourSpace/src/hooks
temp_repos/The-YourSpace/src/components
temp_repos/The-YourSpace/src/contexts
temp_repos/The-YourSpace/src/index.css
temp_repos/The-YourSpace/src/vite-env.d.ts
temp_repos/The-YourSpace/src/lib
temp_repos/The-YourSpace/src/main.tsx
temp_repos/The-YourSpace/src/pages
temp_repos/The-YourSpace/tsconfig.json
```

## Tech Stack (package.json)
```json
{
  "name": "react_repo",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "pnpm install --prefer-offline && vite",
    "build": "pnpm install --prefer-offline && rm -rf node_modules/.vite-temp && tsc -b && vite build",
    "build:prod": "pnpm install --prefer-offline && rm -rf node_modules/.vite-temp && tsc -b && BUILD_MODE=prod vite build",
    "lint": "pnpm install --prefer-offline && eslint .",
    "preview": "pnpm install --prefer-offline && vite preview",
    "install-deps": "pnpm install --prefer-offline",
    "clean": "rm -rf node_modules .pnpm-store pnpm-lock.yaml && pnpm store prune"
  },
  "dependencies": {
    "@hookform/resolvers": "^3.10.0",
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
    "@stripe/react-stripe-js": "^5.3.0",
    "@stripe/stripe-js": "^8.2.0",
    "@supabase/supabase-js": "^2.78.0",
    "class-variance-authority": "^0.7.1",
    "clsx": "^2.1.1",
    "cmdk": "1.0.0",
    "date-fns": "^3.0.0",
    "embla-carousel-react": "^8.5.2",
    "input-otp": "^1.4.2",
    "lucide-react": "^0.364.0",
    "next-themes": "^0.4.4",
    "react": "^18.3.1",
    "react-day-picker": "8.10.1",
    "react-dom": "^18.3.1",
    "react-hook-form": "^7.54.2",
    "react-player": "^3.3.3",
    "react-resizable-panels": "^2.1.7",
    "react-router-dom": "^6",
    "recharts": "^2.12.4",
    "sonner": "^1.7.2",
    "tailwind-merge": "^2.6.0",
    "tailwindcss-animate": "^1.0.7",
    "vaul": "^1.1.2",
    "zod": "^3.24.1"
  },
  "devDependencies": {
    "@eslint/js": "^9.15.0",
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
    "postcss": "8.4.49",
    "tailwindcss": "v3.4.16",
    "typescript": "~5.6.2",
    "typescript-eslint": "^8.15.0",
    "vite": "^6.0.1",
    "vite-plugin-source-identifier": "1.1.2"
  }
}```
