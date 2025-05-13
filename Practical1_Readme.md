# Practical 1: TikTok Clone with Next.js

## Project Overview
A responsive TikTok-like web application built with Next.js, featuring video feeds, user profiles, and authentication forms.

## Features
- Video feed with placeholder content
- Sidebar navigation
- Responsive layout with Tailwind CSS
- Login/Signup forms with validation
- Profile and upload pages

## Setup Instructions

### Prerequisites
- Node.js (v18 or later)
- npm (v9 or later)

### Installation
1. Clone the repository:
   ```bash
   git clone [your-repo-url]
   cd [project-directory]
   ```

2. Install dependencies:
```bash
npm install
```

3. Run the development server:
```bash
npm run dev
```

4. Open your browser at:
http://localhost:3000

## Project Structure
src/
├── app/
│   ├── profile/
│   ├── upload/
│   ├── login/
│   ├── signup/
│   └── layout.js
├── components/
│   ├── layout/
│   │   └── MainLayout.jsx
│   └── ui/
│       ├── VideoCard.jsx
│       └── VideoFeed.jsx
└── lib/

## Dependencies
- Next.js (App Router)
- Tailwind CSS
- react-icons
- react-hook-form

## Usage
1. Navigate through the sidebar to different sections:
- Home feed
- Following
- Explore
- Live
- Profile
- Upload

2. Test the authentication forms:
- Try invalid submissions to see validation
- Successful submissions show loading states