# TaskSphere

A scalable web application for managing personal and team tasks efficiently.

## Features

- **User Authentication**: Secure signup, login, and logout with JWT tokens
- **Task Management**: Full CRUD operations on tasks (Create, Read, Update, Delete)
- **Dashboard**: User-friendly interface to view and manage tasks
- **Search & Filter**: Find tasks quickly by title, status, or priority
- **Profile Management**: View and update user profile information
- **Responsive Design**: Works seamlessly on desktop and mobile devices

## Tech Stack

### Frontend
- React.js with React Router for navigation
- TailwindCSS for styling
- Axios for API calls
- JWT for authentication

### Backend
- Node.js with Express.js
- MongoDB with Mongoose ODM
- JWT for authentication
- bcryptjs for password hashing
- Express Validator for input validation

## Project Structure

```
tasksphere/
├── client/                 # React frontend
│   ├── public/
│   ├── src/
│   │   ├── components/     # React components
│   │   ├── services/       # API service functions
│   │   ├── utils/          # Utility functions
│   │   └── App.js
│   └── package.json
├── server/                 # Express backend
│   ├── config/             # Database configuration
│   ├── middleware/         # Authentication middleware
│   ├── models/             # MongoDB models
│   ├── routes/             # API routes
│   ├── package.json
│   └── server.js
└── README.md
```

## Getting Started

### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local or cloud instance)
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd tasksphere
   ```

2. **Backend Setup**
   ```bash
   cd server
   npm install
   ```

   Create a `.env` file in the server directory:
   ```
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/tasksphere
   JWT_SECRET=your-super-secret-jwt-key
   ```

   Start the backend server:
   ```bash
   npm start
   ```

3. **Frontend Setup**
   ```bash
   cd ../client
   npm install
   npm start
   ```

4. **Access the Application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000

## API Endpoints

### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile (protected)

### Tasks (Protected Routes)
- `GET /api/tasks` - Get all user tasks (with optional search/filter)
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/:id` - Update a task
- `DELETE /api/tasks/:id` - Delete a task

See `TaskSphere.postman_collection.json` for detailed API documentation and examples.

## Security Features

- Password hashing with bcryptjs
- JWT token-based authentication
- Protected routes with middleware
- Input validation and sanitization
- CORS enabled for cross-origin requests

## Scalability Notes

### Frontend Scaling
- **Component Modularization**: Components are designed to be reusable and modular, making it easy to add new features without affecting existing code.
- **State Management**: Currently using local component state. For larger applications, consider implementing Redux or Context API for global state management.
- **Code Splitting**: React.lazy() and Suspense can be used for code splitting to improve initial load times.
- **Progressive Web App (PWA)**: Can be enhanced to work offline and provide a native app-like experience.

### Backend Scaling
- **Database Indexing**: Add indexes on frequently queried fields (user, status, priority) for better query performance.
- **Caching**: Implement Redis for caching frequently accessed data.
- **Rate Limiting**: Add rate limiting to prevent abuse of API endpoints.
- **Load Balancing**: Deploy multiple instances behind a load balancer for horizontal scaling.
- **Microservices**: Split into separate services (auth, tasks, notifications) as the application grows.

### Deployment Considerations
- **Containerization**: Use Docker for consistent deployment across environments.
- **CI/CD**: Implement automated testing and deployment pipelines.
- **Monitoring**: Add logging and monitoring with tools like Winston and PM2.
- **Database Sharding**: For very large datasets, consider database sharding.

## Testing

### Backend Testing
```bash
cd server
npm test
```

### Frontend Testing
```bash
cd client
npm test
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License.
