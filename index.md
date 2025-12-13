![ci-badge](https://github.com/manoa-roomie-match/roomie-app/actions/workflows/ci.yml/badge.svg)

# Roomie Match Manoa
*A roommate matching web application for UH Mānoa students.*

## Team Documents
* [Team Contract](https://docs.google.com/document/d/1kkM3fMJxmjPPykiLTiCI3KJwdg8U3S4DGavawSSr35Y/edit?usp=sharing)
* [GitHub Organization](https://github.com/manoa-roomie-match)
* [Deployment](https://roomie-app-black.vercel.app/)
* [M1 Project Issues](https://github.com/orgs/manoa-roomie-match/projects/1/views/1)
* [M2 Project Issues](https://github.com/orgs/manoa-roomie-match/projects/2/views/1)
* [M3 Project Issues](https://github.com/orgs/manoa-roomie-match/projects/3/views/1)
* [Team Risk Management](https://docs.google.com/document/d/1nVvITUlGXda6MPxVYiWW8BTZ6w7ttYSeM-djZiJQI1I/edit?usp=sharing)

## Table of Contents
* [Overview](#overview)
* [System Objectives and Features](#system-objectives-and-features)
* [User Guide](#user-guide)
* [Community Feedback](#community-feedback)
* [Developer Guide](#dev-guide)

## Overview
The goal of Roomie Match Manoa is to create a user-friendly web application that helps students at the University of Hawaiʻi at Mānoa connect with compatible roommates. The platform aims to simplify the process of finding suitable living arrangements by matching students based on shared preferences, lifestyle habits, and housing interests. By providing an accessible and secure environment for students to interact and form connections, Roomie Match Manoa seeks to improve the overall campus living experience and promote positive roommate relationships.

## System Objectives and Features
The web application will eventually provide the following functionalities:

1. **User Accounts and Profiles**
   - Students can create personal accounts using their university email and build detailed profiles.
   - Profiles include details such as major, interests, and lifestyle preferences.
   - Users can update profiles at any time.
1. **Roommate Matching Algorithm**
   - The system will analyze user-inputted preferences and suggest compatible matches.
     - Potential features the algorithm may take into account are: shared lifestyle preferences, study and sleep habits, major, etc.
1. **Search and Filter Options**
   - Users can search for roommates manually using filters such as major, housing type, or gender preference.
   - Filtered results help users explore beyond automatic matches.
1. **Messaging and Connection Tools**
   - Once matched, users can communicate through an in-app chat feature.
   - Connection requests and message notifications help users stay engaged.
1. **Privacy and Safety Controls**
   - Users can choose what personal details are visible to others.
   - Moderation and reporting features ensure safe interactions.
1. **Responsive and Accessible Design**
   - The platform is optimized for both desktop and mobile use.
   - Accessibility features ensure inclusivity for all students.
1. **Chatbot Assistant**
   - An integrated chatbot will guide users through profile setup and matching.
   - The chatbot will answer FAQs and help users navigate the platform efficiently.
  
## User Guide

This user guide walks a user through the Roomie Match web application. Each section below describes a page, what you can do on that page, and includes a placeholder screenshot link you can replace with an actual image when available.

Base URL: `[http://localhost:3000](https://roomie-app-black.vercel.app)`.

---

### Home (/)

- What you see: Welcome hero, call-to-action buttons, and feature cards describing Matching, Search, and Messaging.
- What you can do: From the home page you can sign up (`/auth/signup`) or learn more. If already signed in you'll see shortcuts to your profile, matches, and messages.
- Screenshot:

![Home Page Screenshot](/images/home.png)

Short description: Use the Home page to get started — register or sign in, and follow links to create your profile or view matches.

---

### Sign Up (/auth/signup)

- What you see: Registration form (Email, Password, Confirm Password).
- What you can do: Create a new account (UH email recommended), which will sign you in and redirect to the Add page. Validation is enforced on required fields and password length.
- Screenshot:

![Sign Up Screenshot](/images/signup.png)

Steps:
- Enter your UH email and a password.
- Click **Register**. After successful registration you are signed in and redirected.

---

### Sign In (/auth/signin)

- What you see: Sign-in form (Email and Password).
- What you can do: Sign in to your account. After successful sign-in you'll be redirected to the home page or a configured callback URL.
- Screenshot:

![Sign In Screenshot](/images/signin.png)

Notes: If you do not have an account, use the link to the Sign Up page.

---

### Sign Out (/auth/signout)

- What you see: Confirmation page asking if you want to sign out.
- What you can do: Confirm sign out (returns to home) or cancel.
- Screenshot:

![Sign Out Screenshot](/images/signout.png)

---

### Change Password (/auth/change-password)

- What you see: Change password form requiring old password, new password, and confirm new password.
- What you can do: Update your password. Client-side validation is provided and a success message displays on completion.
- Screenshot:

![Change Password Screenshot](/images/change-password.png)

---

### Create Profile (/create-profile) & Edit Profile (/edit-profile)

- What you see: Pages for creating or editing your student profile. Currently these pages include an illustrative image and are behind authentication.
- What you can do: Access the UI to create or edit your profile. (The edit page primarily links to the profile-edit flow; profile data is saved via the API.)
- Screenshot:

![Create Profile Screenshot](/images/create-profile.png)

Notes: Profile creation and editing require you to be signed in.

---

### Home (/)

- What you see: An updated home page after being logged in.
- What you can do: View matches, messages, and your profile.
- Screenshot:

![Messaging Screenshot](/images/logged-in-home.png)

---

### My Profile (/user-profile)

- What you see: Your profile card with picture, name, major, email, bio, completeness progress bar, cleanliness and noise ratings, and hobbies badges.
- What you can do: View your profile details, see profile completeness, and click the **Edit Profile** button to update information.
- Screenshot:

![User Profile Screenshot](/images/user-profile.png)

Tips: If your profile is incomplete you'll see a badge and a prompt to complete it.

---

### View Roommates (/view-roommates)

- What you see: A list of student profiles (names, majors, ratings, and profile pictures) presented via the roommate list component.
- What you can do: Browse other students, view basic details, and use provided actions to contact or match (where available).
- Screenshot:

![View Roommates Screenshot](/images/view-roommates.png)

---

### Messaging (/messages)

- What you see: A list of pending messages and previously sent messages.
- What you can do: View your pending messages and message users back.
- Screenshot:

![Messaging Screenshot](/images/messaging.png)

---

### Admin Pages (/admin)

- What you see: Admin-only listing of all 'stuff' and all users (email, role).
- What you can do: If you have admin privileges, review and manage items and user accounts.

Notes: Admin pages are protected — contact the site administrator if you believe you should have access.

---

### Not Authorized (/not-authorized)

- What you see: A simple message shown when you try to access a protected resource without permission.
- What you can do: Return to a permitted page or sign in with an account that has the required role.

---

### Quick Tips

- Sign in with your UH email for verification and access.
- Complete your profile to improve match recommendations.
- Keep your password secure; use the Change Password page to rotate credentials.
- Use the `Add Stuff` and `List` pages to manage items you can share.

### Reporting Issues or Feedback

- For bugs or feature requests, open an issue in the project repository or contact the maintainers.
- When reporting issues, include:
	- Page URL where the problem occurred
	- Steps to reproduce
	- Browser and OS details
	- (Optional) Screenshot showing the issue

---

## Community Feedback

The overwhelming feedback we recieved from having 5 community members try our website was that the matching felt off. They thought that it either didn't have enough criteria, they didn't feel it would work, or that they would rather scroll through the list of users to find it themselves. That is why we implemented a more thorough matching system. After this implementation, we had users re-test our website and they told us that it felt much more smooth.

Other (positive) comments we received was that the color palatte felt representative of UHM. Additionally, users appreciated the profile picture section, as it helped put faces to names. Finally, all but one user liked the page layout; The one user that didn't got hung up on navigating between pages once they had signed in and thought it should be reorganized. We took that into consideration and implemented minor fixes, but kept the high-level layout the same.

---

## Developer Guide

This document helps a developer download, install, run, and modify the Roomie app locally. It assumes you are working on macOS (zsh), and the project uses Next.js, Prisma (PostgreSQL), and Playwright for tests.

### Prerequisites

- Node.js 18+ installed. Verify with:

```bash
node -v
```
- A PostgreSQL server (local or remote) or Docker available.
- Git for cloning the repository.
- Optional tools: `pnpm` or `npm`, `docker` (if using Docker), and `psql` for DB inspection.

### 1) Download / Clone

Clone the repository locally:

```bash
git clone <repo-remote-url>
cd roomie-app
```

Replace `<repo-remote-url>` with the project Git URL or use your fork/clone.

### 2) Install dependencies

Install node modules with your package manager of choice (examples use `npm`):

```bash
npm install
```

Available npm scripts (see `package.json`):

- `npm run dev` — runs the app in development mode
- `npm run build` — runs `prisma generate` and builds the Next.js app
- `npm start` — runs the production server
- `npm run lint` — runs ESLint
- `npm run playwright-development` — runs Playwright tests

### 3) Configure environment variables

Create a `.env` file in the project root. Minimum variables you will likely need:

```
DATABASE_URL=postgresql://<user>:<password>@localhost:5432/<db_name>
NEXTAUTH_SECRET=<a-secure-random-string>
# Add any other variables your deployment requires (API keys, etc.)
```

For local Postgres using Docker, an example `DATABASE_URL` might be:

```
postgresql://postgres:postgres@localhost:5432/roomie
```

### 4) Database setup (Prisma + PostgreSQL)

The project uses Prisma with PostgreSQL (see `prisma/schema.prisma`). To set up the database locally you can:

- Start Postgres locally using Homebrew or Docker. Docker example:

```bash
docker run --name roomie-postgres -e POSTGRES_PASSWORD=postgres \
	-e POSTGRES_USER=postgres -e POSTGRES_DB=roomie -p 5432:5432 -d postgres:15
```

- Generate Prisma client and apply migrations:

```bash
npx prisma generate
npx prisma migrate dev --name init
```

- Run the project seed script (this project defines a seed in `package.json`):

```bash
npx prisma db seed
```

If you prefer to push the current schema without migrations (quick dev), run `npx prisma db push` instead of `migrate dev`.

### 5) Run the app locally

Start the development server:

```bash
npm run dev
```

Open `http://localhost:3000` in your browser. The app uses Next.js App Router — pages live under `src/app`.

### 6) Running tests

- Playwright tests: `npm run playwright-development` (see `tests/` and `playwright.config.ts`)
- You can re-use Playwright session files in `tests/playwright-auth-sessions/` for authenticated flows.

### 7) Building for production

Build and generate Prisma client with:

```bash
npm run build
```

Start the production server (after `build`):

```bash
npm start
```

### 8) Modifying the system (common developer tasks)

- Pages & routing: Most pages live under `src/app`. Add new routes by creating folders with a `page.tsx` file. Use layout files to share UI.
- Components: Reusable UI components are in `src/components`. Add or update `.tsx` and related `.module.css` files.
- API routes: Server routes are in `src/app/api/*/route.ts`. Edit or add handlers to provide backend endpoints.
- Database models: Edit `prisma/schema.prisma`, then run `npx prisma migrate dev` (or `db push` for quick updates), and `npx prisma generate`.
- Authentication: NextAuth is configured in `src/app/api/auth/[...nextauth]/route.ts` and `lib/authOptions.ts`. Update providers or callbacks there.

### 9) Formatting & linting

- ESLint: `npm run lint`
- Prettier is installed — use your editor integration or run it manually as part of your workflow.

### 10) Troubleshooting & tips

- If DB connection fails, verify `DATABASE_URL`, Postgres is running, and port is available.
- If migrations are out-of-sync, run `npx prisma migrate resolve` or carefully inspect `prisma/migrations`.
- If auth or session cookies are failing, confirm `NEXTAUTH_SECRET` is set and matches between environments.
- Use browser dev tools and server logs (`npm run dev` console output) when debugging runtime errors.
