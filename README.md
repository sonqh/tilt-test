# Fullstack Project with Tilt, Kubernetes, and Docker

This project is a fullstack application using Tilt for development, Kubernetes for service management, and Docker for containerization. It includes a NestJS backend and a React frontend.

## Overview

This project is a full-stack web application composed of two main components:

- **Backend**: Built using [NestJS](https://nestjs.com), a progressive Node.js framework for building efficient, reliable, and scalable server-side applications.
- **Frontend**: Built using [React](https://reactjs.org) with [Vite](https://vitejs.dev) as the build tool, providing fast HMR and optimized builds.

## Prerequisites

- Node.js (v22-alpine3.19)
- Docker
- Kubernetes
- Tilt
- pnpm

---

## Backend Setup

### Description

The backend is built with NestJS and integrates with GraphQL for data querying and mutations. Prisma is used for database access.

### Installation

1. Clone the repository and navigate to the backend folder:

   ```bash
   git clone https://github.com/sonqh/fullstack-backend.git
   cd fullstack-backend
   ```

2. Install dependencies using `pnpm`:

   ```bash
   pnpm install
   ```

3. Set up the database by configuring Prisma:

   ```bash
   pnpm prisma migrate dev
   ```

4. Start the development server:
   ```bash
   pnpm start:dev
   ```

### Scripts

- `pnpm build`: Builds the application
- `pnpm start`: Starts the application
- `pnpm start:dev`: Starts the application in watch mode
- `pnpm lint`: Lints the code
- `pnpm test`: Runs unit tests

### GraphQL Schema

Refer to the `src/schema.graphql` file for the API schema.

---

## Frontend Setup

### Description

The frontend is a React application built using Vite. It integrates Apollo Client for GraphQL data fetching.

### Installation

1. Clone the repository and navigate to the frontend folder:

   ```bash
   git clone https://github.com/sonqh/fullstack-frontend.git
   cd fullstack-frontend
   ```

2. Install dependencies using `pnpm`:

   ```bash
   pnpm install
   ```

3. Start the development server:
   ```bash
   pnpm dev
   ```

### Scripts

- `pnpm dev`: Runs the app in development mode
- `pnpm build`: Builds the app for production
- `pnpm preview`: Serves the production build
- `pnpm lint`: Runs ESLint to analyze the code
- `pnpm format`: Formats the code using Prettier

### Apollo Client Setup

Apollo Client is configured in `src/main.jsx`:

```jsx
import { ApolloProvider, ApolloClient, InMemoryCache } from "@apollo/client";

const client = new ApolloClient({
  uri: "http://localhost:3000/graphql",
  cache: new InMemoryCache(),
});

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <ApolloProvider client={client}>
      <App />
    </ApolloProvider>
  </React.StrictMode>
);
```

---

## Shared Resources

- **GraphQL**: Both the frontend and backend rely on GraphQL for API communication. Ensure that the backend server is running before testing frontend queries or mutations.
- **ESLint and Prettier**: Used across the stack for code consistency and style.
- **pnpm**: Ensure you have `pnpm` installed globally for managing dependencies in both projects.

---

## Development Workflow

1. Start the backend server:

   ```bash
   cd fullstack-backend
   pnpm start:dev
   ```

2. Start the frontend server:

   ```bash
   cd fullstack-frontend
   pnpm dev
   ```

3. Open the frontend in your browser at [http://localhost:3000](http://localhost:3000).

---

## Learn More

- [NestJS Documentation](https://docs.nestjs.com)
- [React Documentation](https://reactjs.org/)
- [Vite Documentation](https://vitejs.dev/guide/)
- [Apollo Client Documentation](https://www.apollographql.com/docs/react/)

---

## License

This project is licensed under the MIT License.
