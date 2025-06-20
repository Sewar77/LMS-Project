# EduFlex LMS Project

A full-featured Learning Management System (LMS) backend built with Node.js, Express, and PostgreSQL.

---

## Features

- **User Authentication & Authorization**
  - JWT-based authentication
  - Role-based access control (admin, instructor, student)
  - Google OAuth support

- **Course Management**
  - Courses, modules, lessons, assignments, quizzes, categories
  - CRUD operations for all resources
  - File upload support for assignment submissions (optional)

- **Assignments & Submissions**
  - Students can submit assignments (file or URL)
  - Instructors can grade and provide feedback

- **Quizzes**
  - Multiple-choice quizzes with options and correct answers

- **Categories**
  - Organize courses and content by category

- **API Security**
  - Rate limiting, CORS, helmet, and secure session management

- **Comprehensive Validation**
  - Joi schemas for all input validation

- **Error Handling**
  - Centralized error and not-found middleware

---

## Getting Started

### Prerequisites

- Node.js (v18+ recommended)
- PostgreSQL database

### Installation

1. **Clone the repository**
   ```sh
   git clone https://github.com/yourusername/lms-project.git
   cd lms-project
   ```

2. **Install dependencies**
   ```sh
   npm install
   ```

3. **Configure environment variables**

   Create a `.env` file in the root directory with the following (example):

   ```
   PORT=5000
   DATABASE_URL=postgres://user:password@localhost:5432/lmsdb
   SESSION_SECRET=your_session_secret
   JWT_SECRET=your_jwt_secret
   CORS_ORIGIN=http://localhost:3000
   NODE_ENV=development
   ```

4. **Set up the database**

   - Run the SQL scripts in `/db/schema.sql` or use your migration tool to create tables.

5. **Start the server**
   ```sh
   npm run dev
   ```

---

## API Overview

- **Authentication:**  
  `POST /api/auth/register`  
  `POST /api/auth/login`  
  `POST /api/auth/refresh-token`

- **Users:**  
  `GET /api/users/:id`

- **Courses, Modules, Lessons:**  
  `GET /api/courses`  
  `POST /api/courses` (admin/instructor only)  
  ...and similar for modules and lessons

- **Assignments:**  
  `POST /api/assignments` (instructor/admin only)  
  `GET /api/assignments/:id`  
  `PUT /api/assignments/:id` (instructor/admin only)  
  `DELETE /api/assignments/:id` (instructor/admin only)

- **Submissions:**  
  `POST /api/submissions` (student only)  
  `GET /api/assignments/:assignment_id/submissions` (instructor/admin only)

- **Quizzes:**  
  `POST /api/quizzes` (instructor/admin only)  
  `GET /api/quizzes/:id`

- **Categories:**  
  `POST /api/categories` (admin only)  
  `GET /api/categories`

---

## Testing

- Use [Postman](https://www.postman.com/) or similar tools to test endpoints.
- Sample JSON bodies for requests are provided in the documentation and code comments.

---

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a pull request

---

## License

This project is licensed under the MIT License.

---

## Contact

For questions or support, open an issue or contact the maintainer.