# Notionary

A smart quiz generation application that transforms your Notion notes into interactive quizzes using AI.

## Refactored for CloudFlare

- **Refactoring original project from local computer to use with CloudFlare application**
- **DISCLAIMER:** .env file with environment variables for all the API keys used was not pushed.

## Features

- **Notion Integration**: Seamlessly connects to your Notion database
- **AI-Powered Quiz Generation**: Uses Groq AI (Llama model) to create engaging quizzes
- **Multiple Question Types**: Supports both multiple-choice and free-response questions
- **Modern Web Interface**: Built with Next.js and styled with Tailwind CSS
- **Real-time Processing**: Intelligent caching to optimize API usage

## Project Structure

```
notionary/
├── backend/                 # Express.js API server
│   ├── server.js           # Main server file
│   ├── controllers/        # API controllers
│   ├── routes/            # API routes
│   ├── services/          # Business logic (Notion integration)
│   └── .env               # Environment variables
├── frontend/frontend/      # Next.js application
│   ├── app/               # Next.js 13+ app directory
│   ├── components/        # React components
│   ├── lib/               # Utility functions
│   └── public/            # Static assets
└── README.md              # This file
```

## Quick Start

### Prerequisites

- **Node.js** (v16 or higher)
- **npm** or **yarn**
- **Notion API** access
- **Groq API** key

### 1. Clone and Setup

```bash
# Navigate to the project directory
cd notionary-hackathon/notionary
```

### 2. Install Dependencies

**Backend:**

```powershell
cd backend
npm install
```

**Frontend:**

```powershell
cd frontend/frontend
npm install
```

### 3. Environment Configuration

The project comes with a pre-configured `.env` file in the `backend/` directory with:

- Notion API credentials
- Groq AI API key
- Database configuration

### 4. Run the Application

**Option A: Manual Start (Recommended)**

Open two terminal windows:

**Terminal 1 - Backend Server:**

```powershell
cd backend
node server.js
```

**Terminal 2 - Frontend Server:**

```powershell
cd frontend/frontend
npm run dev
```

**Option B: One-liner Commands**

**Backend:**

```powershell
cd backend; node server.js
```

**Frontend:**

```powershell
cd frontend/frontend; npm run dev
```

### 5. Access the Application

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:3001
- **Quiz Endpoint**: http://localhost:3001/api/quiz

## Usage

1. **Open your browser** and navigate to `http://localhost:3000`
2. **Login** to access the application
3. **Select Notes** from your connected Notion database
4. **Generate Quiz** - AI will create questions based on your notes
5. **Take the Quiz** and view your results

## Available Scripts

### Backend Scripts

- `node server.js` - Start the Express server

### Frontend Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## API Endpoints

- `GET /api/quiz` - Generate and retrieve quiz questions
  - Returns cached results if available (5-minute cache)
  - Generates new quiz from Notion data if cache expired

## Architecture

### Backend (Port 3001)

- **Express.js** server with CORS enabled
- **Notion API** integration for data fetching
- **Groq AI** integration for quiz generation
- **Caching system** to optimize API calls
- **RESTful API** design

### Frontend (Port 3000)

- **Next.js 14** with App Router
- **React 18** with modern hooks
- **Tailwind CSS** for styling
- **shadcn/ui** component library
- **TypeScript** for type safety

## Environment Variables

The following environment variables are configured in `backend/.env`:

```env
NOTION_TOKEN=your_notion_token
NOTION_DATABASE_ID=your_database_id
GROQ_API_KEY=your_groq_api_key
PORT=5000
OPENAI_API_KEY=your_openai_key (optional)
```

## Stopping the Application

To stop the servers:

1. Press `Ctrl+C` in each terminal window
2. Both backend and frontend servers will shut down gracefully

## Troubleshooting

### Common Issues

1. **Port Already in Use**

   - Make sure ports 3000 and 3001 are available
   - Kill existing processes if needed

2. **Dependencies Issues**

   - Run `npm install` in both backend and frontend directories
   - Clear npm cache: `npm cache clean --force`

3. **API Connection Issues**
   - Verify environment variables in `backend/.env`
   - Check network connectivity
   - Ensure API keys are valid

### Logs and Debugging

- Backend logs appear in the terminal where `node server.js` is running
- Frontend logs appear in both terminal and browser console
- Check browser Network tab for API call debugging

## Development

### Adding New Features

1. **Backend**: Add new routes in `routes/`, controllers in `controllers/`
2. **Frontend**: Add new pages in `app/`, components in `components/`

### Code Quality

- ESLint configured for both frontend and backend
- Prettier recommended for code formatting
- TypeScript enabled in frontend for type safety

## Dependencies

### Backend

- Express.js - Web framework
- Groq SDK - AI integration
- Axios - HTTP client
- CORS - Cross-origin requests
- dotenv - Environment variables

### Frontend

- Next.js - React framework
- Tailwind CSS - Styling
- shadcn/ui - UI components
- Radix UI - Accessible components
- TypeScript - Type safety

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License.

---

**Made with ❤️ for transforming learning through AI-powered quizzes**
