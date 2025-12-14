# Smart Learning System - Summarize & Generate Quiz

A comprehensive learning platform that allows users to watch educational videos, generate summaries, create quizzes, and manage playlists. Built with React and Node.js, featuring AI-powered summarization and quiz generation using Google Gemini AI.

## 🚀 Features

- **Video Learning**: Watch educational videos with integrated video player
- **AI Summarization**: Automatically generate summaries of video content using Google Gemini AI
- **Quiz Generation**: Create interactive quizzes from video content
- **Playlist Management**: Create and manage custom playlists
- **User Authentication**: Secure Google OAuth authentication
- **Dashboard**: Track learning progress and statistics
- **Transcript Support**: View video transcripts in multiple languages
- **Feed**: Browse and discover educational content

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library
- **Vite** - Build tool and dev server
- **React Router DOM** - Routing
- **Tailwind CSS** - Styling
- **Framer Motion** - Animations
- **Recharts** - Data visualization
- **Axios** - HTTP client
- **Lucide React** - Icons

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database (via Mongoose)
- **Passport.js** - Authentication middleware
- **Google OAuth 2.0** - Authentication
- **Google Gemini AI** - AI summarization and quiz generation
- **YouTube Transcript API** - Video transcript fetching
- **Python Scripts** - Transcript processing

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- **Node.js** (v18 or higher)
- **npm** or **yarn**
- **MongoDB** (local or MongoDB Atlas)
- **Python** (for transcript processing)
- **Google Cloud Account** (for OAuth and Gemini API)

## 🔧 Installation

### 1. Clone the repository

```bash
git clone <repository-url>
cd Smart_learning_system-summarise-generate_quiz
```

### 2. Install Frontend Dependencies

```bash
cd frontend
npm install
```

### 3. Install Backend Dependencies

```bash
cd ../server
npm install
```

### 4. Environment Setup

#### Frontend Environment Variables

Create a `.env` file in the `frontend` directory:

```env
VITE_API_URL=http://localhost:8000
VITE_SERVER_URL=http://localhost:8000
```

#### Backend Environment Variables

Create a `.env` file in the `server` directory:

```env
# Server Configuration
PORT=8000
SERVER_URL=http://localhost:8000
CLIENT_URL=http://localhost:5173
NODE_ENV=development

# Database
MONGO_URI=mongodb://localhost:27017/learnstream

# Authentication (Google OAuth)
GOOGLE_CLIENT_ID=your_google_client_id
GOOGLE_CLIENT_SECRET=your_google_client_secret
SESSION_SECRET=your_session_secret

# AI Services (Gemini)
SUMMARY_API_KEY=your_gemini_api_key
QUIZ_API_KEY=your_gemini_api_key

# External APIs
YOUTUBE_API_KEY=your_youtube_api_key

# Transcript Service
PYTHON_BIN=python
TRANSCRIPT_LANGS=en,en-US,en-GB,en-IN,hi
```

### 5. Google OAuth Setup

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select an existing one
3. Enable Google+ API
4. Create OAuth 2.0 credentials
5. Add authorized redirect URIs:
   - `http://localhost:8000/auth/google/callback` (development)
   - Your production URL (production)
6. Copy `Client ID` and `Client Secret` to your `.env` file

### 6. Google Gemini API Setup

1. Go to [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create a new API key
3. Add the API key to your `.env` file for `SUMMARY_API_KEY` and `QUIZ_API_KEY`

### 7. YouTube API Setup (Optional)

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Enable YouTube Data API v3
3. Create an API key
4. Add the API key to your `.env` file

## 🚀 Running the Application

### Development Mode

#### Start the Backend Server

```bash
cd server
npm start
```

The server will run on `http://localhost:8000`

#### Start the Frontend Development Server

```bash
cd frontend
npm run dev
```

The frontend will run on `http://localhost:5173`

### Production Build

#### Build Frontend

```bash
cd frontend
npm run build
```

#### Start Production Server

```bash
cd server
npm start
```

## 📁 Project Structure

```
Smart_learning_system-summarise-generate_quiz/
├── frontend/
│   ├── src/
│   │   ├── components/      # Reusable components
│   │   ├── pages/           # Page components
│   │   ├── context/         # React context providers
│   │   ├── hooks/           # Custom React hooks
│   │   └── ...
│   ├── public/              # Static assets
│   └── package.json
│
├── server/
│   ├── src/
│   │   ├── config/          # Configuration files
│   │   ├── middleware/      # Express middleware
│   │   ├── models/          # MongoDB models
│   │   ├── routes/          # API routes
│   │   ├── services/        # Business logic services
│   │   └── utils/           # Utility functions
│   ├── scripts/             # Python scripts
│   ├── server.js            # Entry point
│   └── package.json
│
└── README.md
```

## 🔌 API Endpoints

### Authentication
- `GET /auth/google` - Initiate Google OAuth login
- `GET /auth/google/callback` - Google OAuth callback
- `GET /auth/logout` - Logout user
- `GET /auth/user` - Get current user

### Playlists
- `GET /api/playlists` - Get all playlists
- `POST /api/playlists` - Create a new playlist
- `GET /api/playlists/:id` - Get playlist by ID
- `PUT /api/playlists/:id` - Update playlist
- `DELETE /api/playlists/:id` - Delete playlist

### Videos
- `GET /api/videos/transcript/:videoId` - Get video transcript
- `POST /api/videos/transcript` - Fetch transcript

### AI Services
- `POST /api/ai/summarize` - Generate video summary
- `POST /api/ai/quiz` - Generate quiz from content

### Feed
- `GET /api/feed` - Get video feed

### User
- `GET /api/user/profile` - Get user profile
- `POST /api/user/track` - Track user activity

## 🎯 Key Features Explained

### Video Summarization
Uses Google Gemini AI to analyze video transcripts and generate concise summaries of the content.

### Quiz Generation
Automatically creates interactive quizzes based on video content, helping users test their understanding.

### Playlist Management
Users can create custom playlists, add videos, and organize their learning content.

### Transcript Support
Fetches and displays video transcripts in multiple languages for better accessibility.

## 🐛 Troubleshooting

### Common Issues

1. **MongoDB Connection Error**
   - Ensure MongoDB is running
   - Check `MONGO_URI` in `.env` file
   - Verify network connectivity

2. **OAuth Authentication Fails**
   - Verify Google OAuth credentials
   - Check redirect URIs match exactly
   - Ensure cookies are enabled

3. **AI Services Not Working**
   - Verify Gemini API keys are correct
   - Check API quota limits
   - Ensure internet connectivity

4. **Transcript Not Loading**
   - Verify Python is installed
   - Check `PYTHON_BIN` path in `.env`
   - Ensure required Python packages are installed

## 📝 License

