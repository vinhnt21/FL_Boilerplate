# Frontend Structure

> Status: 🔒 LOCKED
> Version: v1.0
> Locked by: [Your Name]
> Locked at: YYYY-MM-DD
> Note: Frontend architecture and component structure

## Tech Stack
- **Framework:** React/Vue/Angular
- **Styling:** CSS/Tailwind/Styled Components
- **State Management:** Redux/Vuex/Zustand
- **Build Tool:** Vite/Webpack
- **Package Manager:** npm/yarn/pnpm

## Project Structure
```
src/
├── components/
│   ├── common/
│   │   ├── Button/
│   │   ├── Input/
│   │   └── Modal/
│   ├── layout/
│   │   ├── Header/
│   │   ├── Sidebar/
│   │   └── Footer/
│   └── features/
│       ├── auth/
│       ├── dashboard/
│       └── profile/
├── pages/
│   ├── Home/
│   ├── Login/
│   ├── Dashboard/
│   └── Profile/
├── services/
│   ├── api.js
│   └── auth.js
├── utils/
│   ├── constants.js
│   └── helpers.js
├── hooks/
│   ├── useAuth.js
│   └── useApi.js
└── styles/
    ├── globals.css
    └── components.css
```

## Component Guidelines
- Use functional components with hooks
- Keep components small and focused
- Use TypeScript for type safety
- Follow naming conventions: PascalCase for components

## State Management
- Global state: [Redux/Vuex/Zustand]
- Local state: useState/useReducer
- Server state: React Query/SWR

## Routing
- Use React Router/Vue Router
- Implement protected routes
- Add route guards for authentication

## Styling Approach
- [CSS Modules/Styled Components/Tailwind]
- Mobile-first responsive design
- Consistent design system
