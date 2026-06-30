https://github.com/VaishnaviMahendran/internship.git
# Zero-waste-Management-
Task Management Application A modern, full-stack task management application built with the MERN stack (MongoDB, Express.js, React, Node.js) featuring a beautiful, responsive UI with gradient designs and smooth animations.

internship
Repository navigation
Code
Issues
Pull requests
Agents
 0 stars
 0 forks
 0 watching
 1 Branch
 0 Tags
 Activity
Public repository
VaishnaviMahendran/internship
Name	
VaishnaviMahendran
VaishnaviMahendran
8 months ago
backend
8 months ago
frontend
8 months ago
.gitignore
8 months ago
APPLICATION_FLOW.md
8 months ago
FINAL_SUMMARY.md
8 months ago
HOW_TO_RUN.md
8 months ago
MONGODB_SETUP.md
8 months ago
QUICK_START.md
8 months ago
README.md
8 months ago
RUN_COMMANDS.md
8 months ago
Repository files navigation
README
Task Management Application
A modern, full-stack task management application built with the MERN stack (MongoDB, Express.js, React, Node.js) featuring a beautiful, responsive UI with gradient designs and smooth animations.

🌟 Features
User Authentication: Secure registration and login with JWT tokens
Task Management: Create, read, update, and delete tasks
Task Filtering: Filter tasks by status (completed/pending) and priority
Task Sorting: Sort tasks by date, priority, or creation time
Priority Levels: Low, Medium, and High priority tasks with color coding
Due Dates: Set and track task deadlines
Responsive Design: Beautiful UI that works on all devices
Modern UI: Gradient backgrounds, smooth animations, and glass-morphism effects
Real-time Updates: Instant task updates without page refresh
🛠️ Tech Stack
Frontend
React 18 - UI library
React Router DOM - Client-side routing
Axios - HTTP client
Tailwind CSS - Utility-first CSS framework
Heroicons - Beautiful hand-crafted SVG icons
Vite - Fast build tool and dev server
Backend
Node.js - Runtime environment
Express.js - Web framework
MongoDB - NoSQL database
Mongoose - MongoDB object modeling
JWT - JSON Web Tokens for authentication
bcryptjs - Password hashing
Helmet - Security middleware
Morgan - HTTP request logger
Express Rate Limit - Rate limiting middleware
📋 Prerequisites
Before you begin, ensure you have the following installed:

Node.js (v14 or higher) - Download
MongoDB (v4.4 or higher) - Download
npm or yarn - Package manager (comes with Node.js)
🚀 Getting Started
1. Clone the Repository
git clone <your-repository-url>
cd task-management-app
2. MongoDB Setup
Option A: Local MongoDB Installation
Install MongoDB Community Edition

Download from MongoDB Download Center
Follow the installation instructions for your operating system
Start MongoDB Service

Windows:

# Start MongoDB as a service (if installed as service)
net start MongoDB

# OR run manually
"C:\Program Files\MongoDB\Server\<version>\bin\mongod.exe" --dbpath="C:\data\db"
macOS:

brew services start mongodb-community
Linux:

sudo systemctl start mongod
sudo systemctl enable mongod
Verify MongoDB is Running

# Connect to MongoDB shell
mongosh
# or
mongo
Option B: MongoDB Atlas (Cloud Database)
Go to MongoDB Atlas
Create a free account and cluster
Get your connection string
Update the MONGODB_URI in backend .env file
3. Backend Setup
# Navigate to backend directory
cd backend

# Install dependencies
npm install

# Create .env file (already exists, but verify the settings)
# The .env file should contain:
# PORT=5000
# MONGODB_URI=mongodb://localhost:27017/taskmanagement
# JWT_SECRET=your_super_secret_jwt_key_change_this_in_production_12345
# JWT_EXPIRE=7d
# NODE_ENV=development
# CLIENT_URL=http://localhost:5173

# Start the backend server
npm run dev
The backend server will start on http://localhost:5000

4. Frontend Setup
Open a new terminal window:

# Navigate to frontend directory
cd frontend

# Install dependencies
npm install

# Start the development server
npm run dev
The frontend application will start on http://localhost:5173

🎯 Usage
Register a New Account

Navigate to http://localhost:5173/register
Fill in your name, email, and password
Click "Create Account"
Login

Navigate to http://localhost:5173/login
Enter your email and password
Click "Sign in"
Create Tasks

Once logged in, use the "Create New Task" form on the right
Enter task title, description, priority, and due date
Click "Create Task"
Manage Tasks

Mark as Complete: Click the circle icon next to the task
Edit Task: Click the pencil icon
Delete Task: Click the trash icon
View Details: Click the chevron icon to expand/collapse
Filter and Sort

Use the dropdown menus to filter by status or priority
Sort tasks by newest, oldest, due date, or priority
📁 Project Structure
task-management-app/
├── backend/
│   ├── controllers/
│   │   ├── authController.js      # Authentication logic
│   │   └── taskController.js      # Task CRUD operations
│   ├── middleware/
│   │   └── authMiddleware.js      # JWT verification
│   ├── models/
│   │   ├── User.js                # User schema
│   │   └── Task.js                # Task schema
│   ├── routes/
│   │   ├── authRoutes.js          # Auth endpoints
│   │   └── taskRoutes.js          # Task endpoints
│   ├── utils/
│   │   └── jwtUtils.js            # JWT helper functions
│   ├── .env                       # Environment variables
│   ├── server.js                  # Express server setup
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── Auth/
│   │   │   │   └── ProtectedRoute.jsx
│   │   │   ├── Layout/
│   │   │   │   ├── Header.jsx
│   │   │   │   └── LoadingSpinner.jsx
│   │   │   └── Tasks/
│   │   │       ├── TaskForm.jsx
│   │   │       ├── TaskItem.jsx
│   │   │       └── TaskList.jsx
│   │   ├── context/
│   │   │   ├── AuthContext.jsx    # Authentication state
│   │   │   └── TaskContext.jsx    # Task state management
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx      # Main dashboard
│   │   │   ├── Login.jsx          # Login page
│   │   │   └── Register.jsx       # Registration page
│   │   ├── services/
│   │   │   ├── api.js             # Axios configuration
│   │   │   ├── authService.js     # Auth API calls
│   │   │   └── taskService.js     # Task API calls
│   │   ├── App.jsx                # Main app component
│   │   ├── main.jsx               # Entry point
│   │   └── index.css              # Global styles
│   ├── public/
│   ├── index.html
│   ├── package.json
│   ├── tailwind.config.js
│   └── vite.config.js
│
└── README.md
🔒 Environment Variables
Backend (.env)
PORT=5000
MONGODB_URI=mongodb://localhost:27017/taskmanagement
JWT_SECRET=your_super_secret_jwt_key_change_this_in_production_12345
JWT_EXPIRE=7d
NODE_ENV=development
CLIENT_URL=http://localhost:5173
Important: Change the JWT_SECRET to a strong, random string in production!

Frontend
The frontend uses Vite's environment variable system. Create a .env file in the frontend directory if you need to customize the API URL:

VITE_API_BASE_URL=http://localhost:5000/api
🧪 API Endpoints
Authentication
POST /api/auth/register - Register new user
POST /api/auth/login - Login user
POST /api/auth/logout - Logout user
GET /api/auth/me - Get current user (protected)
Tasks
GET /api/tasks - Get all tasks for current user (protected)
GET /api/tasks/:id - Get single task (protected)
POST /api/tasks - Create new task (protected)
PUT /api/tasks/:id - Update task (protected)
DELETE /api/tasks/:id - Delete task (protected)
Health Check
GET /api/health - Check server status
🎨 Design Features
Gradient Backgrounds: Beautiful gradient color schemes for different pages
Glass Morphism: Modern glass effect on cards and components
Smooth Animations: Fade-in, slide-in, and floating animations
Responsive Layout: Mobile-first design that works on all screen sizes
Color-Coded Priorities: Visual distinction for task priorities
Interactive UI: Hover effects and smooth transitions
🔧 Available Scripts
Backend
npm start       # Start production server
npm run dev     # Start development server with nodemon
Frontend
npm run dev     # Start development server
npm run build   # Build for production
npm run preview # Preview production build
npm run lint    # Run ESLint
🐛 Troubleshooting
MongoDB Connection Issues
Error: "MongoDB connection error"

Ensure MongoDB is running: mongosh or mongo
Check if the port 27017 is available
Verify the MONGODB_URI in .env file
Port Already in Use
Error: "Port 5000 is already in use"

Change the PORT in backend .env file
Or kill the process using port 5000
Windows:

netstat -ano | findstr :5000
taskkill /PID <PID> /F
CORS Errors
Ensure CLIENT_URL in backend .env matches your frontend URL
Check that both servers are running
JWT Token Issues
Clear browser localStorage
Re-login to get a new token
Ensure JWT_SECRET is set in .env
📝 License
This project is open source and available under the MIT License.

👨‍💻 Author
Created with ❤️ for efficient task management

🤝 Contributing
Contributions, issues, and feature requests are welcome!

📧 Support
For support, email your-email@example.com or create an issue in the repository.

Happy Task Managing! 🎉

Releases
No releases published
Packages
No packages published
Contributors
