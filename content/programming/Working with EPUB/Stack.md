 - Docker + Lua for building.
 - Typescript/Angular
 - TRPC
 - Elysia/Bun
 - Prisma
 - Minio


## Configuring Eden with Angular
https://deepwiki.com/search/can-you-please-provide-a-guide_e2a01cbb-82b5-454f-b0c1-f0931279471e



## Configuring  google-auth with Better Auth 

### better-auth in general 
https://deepwiki.com/better-auth/better-auth/2.4-security-and-middleware

### configuration
https://deepwiki.com/search/how-can-i-set-it-up-to-login-w_62ec184b-52cc-477d-9084-9578383d0cb8
```markdown

You're asking about setting up Google authentication for an Angular frontend application using Better Auth. <cite/>

## Setup Overview

To integrate Google login with your Angular app, you'll need to configure both the server-side Better Auth instance and the client-side authentication. <cite/>

## Server Configuration

First, configure Google as a social provider in your Better Auth server setup: [1](#0-0) 

You'll need to obtain Google credentials from the Google Cloud Console and set the redirect URI to `http://localhost:3000/api/auth/callback/google` for development. [2](#0-1) 

## Client Setup for Angular

While the codebase shows React examples, Better Auth provides framework-agnostic client libraries. For Angular, you would use the vanilla JavaScript client: [3](#0-2) 

Create an auth client in your Angular service:
```

```typescript
import { createAuthClient } from "better-auth/client";

export const authClient = createAuthClient({
  // baseURL: "http://localhost:3000" // if different domain
});
```

```markdown

## Implementing Google Sign-In

To trigger Google authentication, use the `signIn.social` method: [4](#0-3) 

The sign-in process supports various options including custom callback URLs and error handling: [5](#0-4) 

## Authentication Flow

When a user initiates Google login, Better Auth handles the OAuth flow automatically: [6](#0-5) 

The process includes CSRF protection via state tokens, optional PKCE for security, and automatic user account creation or linking. [7](#0-6) 

## Additional Options

You can configure additional Google-specific options like always prompting for account selection or requesting offline access for refresh tokens: [8](#0-7) 

## Notes

The codebase primarily shows Next.js/React examples, but Better Auth's client library works with any JavaScript framework including Angular. The core authentication flow and API remain the same regardless of the frontend framework. For Angular-specific reactive patterns, you may need to wrap the auth client methods in Angular services and use RxJS observables for state management.

Wiki pages you might want to explore:
- [Framework Integrations (better-auth/better-auth)](/wiki/better-auth/better-auth#6)
```
