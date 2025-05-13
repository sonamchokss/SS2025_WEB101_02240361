# Practical 4: TikTok Full-Stack Integration

## Project Overview
Connects Next.js frontend to Express.js backend with:
- JWT authentication
- Video feed integration
- User following system
- Interactive video features

## Features
**Authentication**
- Login/registration with JWT
- Protected routes
- Persistent sessions

**Video Features**
- Real video feeds (For You/Following)
- Like/comment functionality
- Video upload interface

**Social System**
- User discovery
- Follow/unfollow
- Profile pages

## Setup Instructions

### Prerequisites
- Node.js (v18+)
- Running backend server (from Practical 3)
- MongoDB database

### Installation
1. Clone both repositories:
   ```bash
   git clone https://github.com/syangche/TikTok_Frontend.git
   git clone https://github.com/syangche/TikTok_Server.git
   ```

2. Configure backend:
```bash
cd TikTok_Server
npm install
cp .env.example .env
# Fill in MongoDB and JWT secrets
npm run dev
```

3. Configure frontend:
```bash
cd TikTok_Frontend
npm install
cp .env.local.example .env.local
# Set API URL (http://localhost:8000/api)
npm run dev
```

4. Access at:
Frontend: http://localhost:3000
Backend: http://localhost:8000

## Key Files Structure
```
TikTok_Frontend/
├── src/
│   ├── contexts/           
│   ├── services/          
│   ├── components/      
│   └── app/ 
│       ├── profile/[id]/
│       ├── following/
│       └── explore-users/

TikTok_Server/
├── src/
│   ├── controllers/      
│   ├── models/          
│   └── routes/          
```

## Testing Guide
1. Authentication
- Register 2+ test users
- Verify login/logout flow

2. Video Interaction
- Upload test videos
- Like/comment from different accounts

3. Social Features
- Follow users from explore page
- Verify Following feed updates

3. Edge Cases
- Test expired tokens
- Verify protected routes