# CollabSpace - Professional Collaboration Platform

A professional project management and collaboration platform with AI-powered suggestions.

## 🚀 Quick Start

### Prerequisites
- Node.js 16+ 
- MongoDB (local or Atlas)
- npm or yarn

### Local Development

#### Backend
```bash
cd backend
npm install
npm start
```
Backend runs on: http://localhost:5000

#### Frontend
```bash
cd frontend
npm install
npm run dev
```
Frontend runs on: http://localhost:5173

## 📦 Deployment to Render

### Using render.yaml (Recommended)

1. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Deploy to Render"
   git push origin main
   ```

2. **Connect to Render**
   - Go to [Render Dashboard](https://dashboard.render.com/)
   - Click "New" → "Blueprint"
   - Connect your GitHub repository
   - Render will automatically detect `render.yaml`

3. **Set Environment Variables**
   In Render Dashboard, set these for the backend service:
   - `MONGODB_URI`: Your MongoDB connection string
   - `JWT_SECRET`: Your secret key
   - `GEMINI_API_KEY`: Your Gemini API key
   - `GEMINI_PROJECT_NAME`: Your Gemini project name
   - `GEMINI_PROJECT_NUMBER`: Your Gemini project number

### Manual Deployment

#### Backend Deployment
1. Create a new Web Service on Render
2. Connect your repository
3. Configure:
   - **Root Directory**: `backend`
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
   - **Environment**: Node
4. Add environment variables (see above)

#### Frontend Deployment
1. Create a new Static Site on Render
2. Connect your repository
3. Configure:
   - **Root Directory**: `frontend`
   - **Build Command**: `npm install && npm run build`
   - **Publish Directory**: `dist`
4. Add environment variable:
   - `VITE_API_URL`: Your backend URL

## 🔐 Environment Variables

### Backend (.env)
```
PORT=5000
MONGODB_URI=your_mongodb_uri
NODE_ENV=production
JWT_SECRET=your_jwt_secret
JWT_EXPIRE=30d
GEMINI_API_KEY=your_gemini_api_key
GEMINI_PROJECT_NAME=your_project_name
GEMINI_PROJECT_NUMBER=your_project_number
```

### Frontend (.env)
```
VITE_API_URL=http://localhost:5000
```

## 📁 Project Structure

```
Collab Space/
├── backend/               # Backend API
│   ├── config/           # Database configuration
│   ├── controllers/      # Request handlers
│   ├── middleware/       # Auth middleware
│   ├── models/          # MongoDB models
│   ├── routes/          # API routes
│   ├── utils/           # AI utilities
│   └── index.js         # Entry point
├── frontend/            # Frontend React app
│   ├── src/
│   │   ├── components/  # React components
│   │   ├── context/     # Context providers
│   │   ├── pages/       # Page components
│   │   └── utils/       # API utilities
│   └── index.html
└── render.yaml          # Render deployment config
```

## ✨ Features

- 🎨 **Professional UI** - Corporate-ready design
- 👥 **Team Collaboration** - Real-time board sharing
- 📋 **Kanban Boards** - Drag-and-drop task management
- 🤖 **AI Suggestions** - Powered by Google Gemini
- 🔐 **Secure Auth** - JWT-based authentication
- 📱 **Responsive** - Works on all devices

## 🛠️ Tech Stack

### Frontend
- React 18
- Vite
- TailwindCSS
- React Router
- React DnD

### Backend
- Node.js
- Express
- MongoDB
- Mongoose
- JWT
- Google Gemini AI

## 📝 License

MIT License - feel free to use for any purpose.
