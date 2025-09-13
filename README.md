# Premier League Match Predictor

A full-stack web application that predicts Premier League match outcomes using machine learning.

## Features

- **Team Selection**: Choose from 20 Premier League teams with authentic logos
- **AI Predictions**: Machine learning-powered match outcome predictions
- **Beautiful UI**: Premier League-themed design with gradient backgrounds
- **Real-time Results**: Instant prediction results with confidence levels
- **Fallback System**: Works even without the ML model backend

## Architecture

### Frontend (Next.js + React + Tailwind)
- Modern React components with TypeScript
- Premier League color scheme (#37003c, #00ff87, #187bcd)
- Responsive design with team logos
- Real-time prediction display

### Backend (FastAPI + Python)
- FastAPI REST API with automatic documentation
- Machine learning model integration (pl_match_model.pkl)
- Intelligent fallback predictions based on team strengths
- CORS enabled for frontend integration

## Getting Started

### 1. Frontend (Next.js)
The frontend is ready to run in the v0 environment. It includes:
- Team selection dropdowns with logos
- Match prediction interface
- Results display with confidence levels

### 2. Backend (FastAPI)
To run the Python backend:

\`\`\`bash
cd scripts
python run_backend.py
\`\`\`

This will:
- Install required Python packages
- Start the FastAPI server on http://localhost:8000
- Provide API documentation at http://localhost:8000/docs

### 3. Machine Learning Model
Place your trained model file `pl_match_model.pkl` in the scripts directory. The system will automatically:
- Load the model if available
- Use intelligent fallback predictions if the model is missing
- Handle errors gracefully

## API Endpoints

- `POST /predict` - Get match predictions
- `GET /teams` - List available teams
- `GET /health` - Health check and model status

## Team Logos

All 20 Premier League team logos are included in `/public/logos/`:
- Arsenal, Manchester City, Liverpool, Chelsea
- Tottenham, Manchester United, Newcastle, Nottingham Forest
- Aston Villa, Brighton, Crystal Palace, Brentford
- Bournemouth, West Ham United, Everton, Fulham
- Wolves, Leeds, Sunderland, Burnley FC

## Environment Variables

- `BACKEND_URL` - FastAPI backend URL (default: http://localhost:8000)

## Technologies Used

- **Frontend**: Next.js 14, React, TypeScript, Tailwind CSS, shadcn/ui
- **Backend**: FastAPI, Python, scikit-learn, joblib, pandas, numpy
- **Deployment**: Vercel (frontend), any Python hosting (backend)

## Development

The application works in three modes:
1. **Full Stack**: Frontend + Backend with ML model
2. **Frontend Only**: Uses Next.js API routes with fallback predictions
3. **Fallback Mode**: Intelligent predictions based on team strengths

This ensures the app always works, regardless of backend availability.
