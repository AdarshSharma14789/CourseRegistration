# CourseRegistration
Course Registration System
Description
The Course Registration System is a full-stack Java application built with Spring Boot, designed to streamline the course registration process for educational institutions. It enables administrators to manage students, professors, semesters, and courses; students to submit course preferences; and automated allocation of courses based on preferences, availability, and student CPI. The system includes user authentication via JWT, password encryption with BCrypt, email notifications for allocations and reminders, and integration with a PostgreSQL database.
Key functionalities include user registration, course management, form submission for course preferences, automatic course allocation, and email-based communications.
Features

User Management: Register and manage admins, students, and professors with role-based access (ADMIN, STUDENT, PROFESSOR).
Course and Semester Management: Admins can create, update, and manage courses and semesters.
Student Registration Forms: Students submit preferred and required courses; forms are processed for allocation.
Automated Allocation: Courses are allocated based on student preferences, required courses, CPI (for prioritization), and seat availability. Emails are sent with allocation results.
Email Notifications: Reminders for form submission and allocation outcomes using JavaMailSender.
Authentication and Security: JWT for token-based authentication, Spring Security for user details and role enforcement, BCrypt for password hashing.
Professor Views: Professors can view their assigned courses.
Database Integration: PostgreSQL for persistent storage of users, courses, forms, etc.

Technologies Used

Backend: Java 17+, Spring Boot, Spring Security, Spring Data JPA, Hibernate
Database: PostgreSQL (hosted on Render or local)
Authentication: JWT (io.jsonwebtoken), BCryptPasswordEncoder
Email: Spring Mail with Gmail SMTP
Build Tool: Maven (inferred from dependencies and structure)
Testing: JUnit with Spring Boot Test
Other Libraries: Lombok (assumed for DTOs), etc.
IDE Recommendation: IntelliJ IDEA (based on provided config files)

Installation

Prerequisites:

Java JDK 17 or higher
Maven 3.6+
PostgreSQL database (set up locally or use a hosted service like Render)
Gmail account for SMTP (or configure another email provider)

Clone the Repository:
git clone https://github.com/AdarshSharma14789/CourseRegistrationSystem.git

Navigate to the Project Directory:
cd CourseRegistrationSystem

Build and Install Dependencies:
mvn clean install

Run the Application:
mvn spring-boot:run

The application will start on http://localhost:8080 (default port).

Usage
This is a RESTful API. Use tools like Postman or curl to interact with endpoints. (Controllers not provided in files, but inferred from services.)
Example Endpoints (Assumed based on services; adjust as per actual controllers):

Login: POST /api/auth/login - Body: { "email": "user@example.com", "password": "pass" } - Returns JWT token.
Register Student: POST /api/admin/register-student (Admin only) - Body: StudentDTO JSON.
Submit Registration Form: POST /api/student/{id}/submit-form - Body: RegistrationFormDTO JSON.
Allocate Courses: POST /api/admin/allocate-courses (Admin only) - Triggers allocation and emails.
Get All Courses: GET /api/student/courses - Returns list of available courses.

Include JWT in headers for authenticated requests: Authorization: Bearer <token>.
Running Tests
mvn test

Contributing
Contributions are welcome! Follow these steps:

Fork the repository.
Create a new branch: git checkout -b feature/your-feature.
Commit your changes: git commit -m "Add your feature".
Push to the branch: git push origin feature/your-feature.
Open a pull request.

Please ensure code follows Java conventions, includes tests, and handles exceptions properly.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or issues, open a GitHub issue or contact [Your Name] at [your.email@example.com].
