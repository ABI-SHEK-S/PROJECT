# FamilyChat 💬

Private family/friends chat app — WhatsApp + Telegram style, LAN/Wi-Fi ready.

## Quick Start

### 1. Install dependencies

cd backend && npm install
cd ../frontend && npm install

### 2. Configure environment

Copy `backend/.env` and set:
- JWT_SECRET (use a long random string!)
- ADMIN_USERNAME / ADMIN_PASSWORD

### 3. Start backend

cd backend
npm run dev        # development
npm start          # production

### 4. Start frontend

cd frontend
# Create .env:
echo "REACT_APP_SERVER_URL=http://<YOUR_LAN_IP>:3001" > .env
npm start          # dev server on :3000

### 5. Production build

cd frontend && npm run build
# Serve the build/ folder via nginx or serve package

## LAN Hosting Guide

1. Find your PC's LAN IP:
   - Windows: ipconfig  (look for IPv4 address)
   - Mac/Linux: ifconfig or ip a

2. Set REACT_APP_SERVER_URL=http://192.168.x.x:3001 in frontend/.env
3. Run npm run build in frontend/
4. Serve: npx serve -s build -p 3000
5. Other devices on the same Wi-Fi can visit http://192.168.x.x:3000

## Default Admin Login

Username: admin
Password: Admin@FamilyChat2024

⚠️ CHANGE THE PASSWORD IMMEDIATELY after first login!

## Admin Powers

- Add / delete / block users
- Create groups
- Upload stickers
- Delete any message
- Send broadcast announcements
- View server analytics

## Tech Stack

- Frontend: React 18, Tailwind CSS, Framer Motion, Socket.IO client
- Backend:  Node.js, Express, Socket.IO, better-sqlite3, JWT, Multer

## Folder recap

backend/   → Node.js API + Socket.IO server
frontend/  → React app

## Security Notes

- Change JWT_SECRET in .env before deploying
- Change default admin password immediately
- Keep this on your LAN — don't expose to the public internet
- File uploads limited to 50MB by default
