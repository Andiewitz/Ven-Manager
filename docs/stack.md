# Tech Stack

## Client (`/client`)

| Technology | Version | Purpose |
|------------|---------|---------|
| SvelteKit | ^2.63.0 | Full-stack framework |
| Svelte | ^5.56.1 | UI components |
| TypeScript | ^6.0.3 | Type safety |
| Sass | ^1.101.0 | CSS preprocessing |
| Vite | ^8.0.16 | Build tooling |
| Tailwind CSS | ^4.0.0 | Utility-first CSS |
| shadcn-svelte | ^1.4.2 | UI component library |
| Bits UI | - | Accessible primitives |
| Lucide | - | Icons |

## Server (`/server`)

| Technology | Version | Purpose |
|------------|---------|---------|
| Node.js | v24.18.0 | Runtime |
| Express | ^5.2.1 | HTTP framework |
| TypeScript | ^7.0.2 | Type safety |
| CORS | ^2.8.6 | Cross-origin requests |
| dotenv | ^17.4.2 | Environment variables |
| tsx | ^4.23.1 | TS execution (dev) |

## DevOps & Tooling (`/`)

| Technology | Version | Purpose |
|------------|---------|---------|
| ESLint | ^10.7.0 | Linting |
| Vitest | ^4.1.10 | Unit/Integration tests |
| concurrently | ^9.1.2 | Parallel dev scripts |
| GitHub Actions | - | CI/CD pipeline |

## Coverage Status

- **Linting**: ESLint with TypeScript rules
- **Testing**: Vitest (unit + integration)
- **CI/CD**: lint → test → build pipeline
- **Type Checking**: TypeScript strict mode (server)
- **UI Components**: shadcn-svelte (Sidebar, Card, Button, Tooltip, etc.)
- **Icons**: Lucide Svelte
- **Styling**: Tailwind CSS 4 with shadcn-svelte CSS variables