# Voting Poll

A lightweight poll app built with Next.js, React, TypeScript, Tailwind CSS, and Stream Chat. Join with a username, create a question with answer options, and vote. Stream Chat carries question and vote updates between connected users.

## Features

- Join with a username.
- Create poll questions with multiple options.
- Vote and view results.
- Receive question and vote updates through a shared Stream Chat channel.
- Use the interface on desktop or mobile screens.

## Requirements

- Node.js 18.18 or later
- npm
- A Stream Chat application and its API key

## Setup

1. Clone or download this repository, then open a terminal in the project folder.
2. Install the dependencies:

   ```bash
   npm ci
   ```

3. Configure Stream Chat. In `src/lib/stream.ts`, replace the `YOUR_API_KEY` placeholder passed to `StreamChat.getInstance` with your Stream Chat API key.
4. Start the development server:

   ```bash
   npm run dev
   ```

5. Open [http://localhost:3000](http://localhost:3000).

The app currently creates Stream development tokens in the browser. This is suitable only for local development and must not be used in production. A production deployment should generate user tokens on a trusted server and keep the Stream API secret out of client-side code.

## Using the app

1. Enter a username on the home page.
2. Create a poll question and provide at least two options.
3. Select an option to vote. Votes and new questions are sent through the shared `voting-session` Stream channel.

Usernames are a simple entry mechanism, not production authentication.

## Project structure

```text
src/
├── app/
│   ├── page.tsx             # Username entry
│   └── vote/
│       ├── page.tsx         # Poll list and voting
│       └── new/page.tsx     # Create a poll
├── components/              # Reusable poll components
├── lib/
│   ├── stream.ts            # Stream Chat connection and channel
│   └── store.ts             # Poll and vote state
└── styles/
    └── globals.css          # Global theme
```

## Useful commands

```bash
npm run dev        # Start the development server
npm run build      # Create a production build
npm start          # Run the production server
npm run lint       # Run ESLint
npm run typecheck  # Run the TypeScript checker
```

Dependencies are recorded in `package.json` and `package-lock.json`.

## License

No license file is currently included. Add or confirm the appropriate license before distributing this project.
