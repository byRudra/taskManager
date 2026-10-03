# Task Manager Application

A modern, full-stack task management application with user authentication, real-time task operations, and a beautiful responsive interface.

## 🚀 Features

### User Management

- User registration and authentication
- Secure login with token-based authentication
- Persistent user sessions
- User profile display

### Task Management

- Create, edit, and delete tasks
- Mark tasks as completed/pending
- Set task priorities (Low, Medium, High)
- Add due dates with overdue indicators
- Rich task descriptions
- Real-time task statistics

### User Interface

- Modern, responsive design
- Beautiful gradient backgrounds and animations
- Priority-based color coding
- Filter tasks by status (All, Pending, Completed)
- Visual feedback for overdue tasks
- Loading states and error handling
- Mobile-friendly interface

## 🛠️ Tech Stack

### Backend

- **Node.js** - JavaScript runtime
- **Express.js** - Web framework
- **bcryptjs** - Password hashing
- **cors** - Cross-origin resource sharing

### Frontend

- **HTML5** - Semantic markup
- **CSS3** - Modern styling with Flexbox/Grid
- **Vanilla JavaScript** - ES6+ features
- **Local Storage** - Client-side persistence

## 📁 Project Structure

```
taskManager/
├── backend/
│   ├── server.js           # Express server & API routes
│   ├── package.json        # Dependencies & scripts
│   └── node_modules/       # Installed packages
├── frontend/
│   ├── index.html          # Main HTML structure
│   ├── script.js           # Client-side logic
│   └── styles.css          # Complete styling
└── README.md               # Project documentation
```

## ⚡ Quick Start

### Prerequisites

- Node.js (v14 or higher)
- npm (comes with Node.js)
- Modern web browser

### 1. Clone the Repository

```bash
git clone https://github.com/byRudra/taskManager
cd taskManager
```

### 2. Setup Backend

```bash
cd backend
npm install
node server.js
```

Server will start on `http://localhost:3000`

### 3. Setup Frontend

```bash
cd ../frontend
# Open index.html in your browser
# OR use a local server:
npx serve .
```

## 🔌 API Reference

### Authentication Endpoints

```
POST /api/auth/register
POST /api/auth/login
GET  /api/auth/me
POST /api/auth/logout
```

### Task Endpoints (Authenticated)

```
GET    /api/tasks           # Get all user tasks
POST   /api/tasks           # Create new task
GET    /api/tasks/:id       # Get specific task
PUT    /api/tasks/:id       # Update task
DELETE /api/tasks/:id       # Delete task
PATCH  /api/tasks/:id/toggle # Toggle completion
```

### Health Check

```
GET /api/health             # Server status
```

## 🔐 Authentication Flow

1. **Registration/Login**: User provides credentials
2. **Token Generation**: Server returns JWT-like token
3. **Token Storage**: Client stores token in localStorage
4. **API Requests**: Token sent in Authorization header
5. **Token Validation**: Server validates token for protected routes

## 💾 Data Models

### User

```javascript
{
  id: number,
  email: string,
  password: string (hashed),
  name: string,
  createdAt: string (ISO date)
}
```

### Task

```javascript
{
  id: number,
  userId: number,
  title: string,
  description: string,
  completed: boolean,
  priority: 'low' | 'medium' | 'high',
  dueDate: string (ISO date) | null,
  createdAt: string (ISO date),
  updatedAt: string (ISO date)
}
```

## 🎨 UI Components

### Authentication Form

- Switch between login/signup modes
- Form validation and error display
- Smooth animations and transitions

### Dashboard

- Header with user info and logout
- Statistics cards (Total, Completed, Pending)
- Filter buttons for task views
- Add task button

### Task Cards

- Priority-based color coding
- Completion checkboxes
- Edit and delete actions
- Due date indicators
- Overdue warnings

### Task Modal

- Create/edit task form
- Priority selection
- Date picker for due dates
- Form validation

## 🔧 Configuration

### Backend Configuration

- Default port: 3000
- CORS enabled for all origins
- In-memory data storage (development)

### Frontend Configuration

- API base URL: `http://localhost:3000/api`
- Token storage: localStorage
- Auto-login on page refresh

## 🚀 Deployment

### Backend

```bash
# Production build
npm start

# Using PM2
npm install -g pm2
pm2 start server.js --name "task-manager-api"
```

### Frontend

```bash
# Static file hosting (Netlify, Vercel, etc.)
# Upload frontend/ directory contents
```

## 🔮 Future Enhancements

### Backend Improvements

- [ ] Database integration (MongoDB/PostgreSQL)
- [ ] JWT token implementation
- [ ] Email verification
- [ ] Password reset functionality
- [ ] Rate limiting and security headers
- [ ] API documentation with Swagger

### Frontend Improvements

- [ ] Task search functionality
- [ ] Drag & drop task reordering
- [ ] Task categories/tags
- [ ] Dark mode toggle
- [ ] Offline support with Service Workers
- [ ] Task export/import
- [ ] Notification system

### DevOps & Testing

- [ ] Unit and integration tests
- [ ] Docker containerization
- [ ] CI/CD pipeline
- [ ] Environment configuration
- [ ] Logging and monitoring

## 🐛 Known Issues

- Data is stored in memory (resets on server restart)
- No input sanitization on backend
- Basic error handling
- No password strength requirements

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🆘 Support

For support, please open an issue on the GitHub repository or contact the development team.

---

**Built with ❤️ using modern web technologies**
