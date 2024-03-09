##Airtribe Backend Internship Assignment
This document provides instructions for setting up and running the backend server for the Airtribe application, as well as details on the database design and APIs implemented.

#Installation
Visual Studio Code Extensions

Make sure you have the following extensions installed in Visual Studio Code:

Code Runner
JavaScript (ES6) code snippets
Node.js

Ensure that Node.js is installed on your system. You can download it from nodejs.org. 
or 
you can install in vs code 


Navigate to the project directory and install the required dependencies:

bash
Copy code
cd airtribe-backend
npm install
Database Design
##The database schema for the Airtribe application is as follows:

Instructors

id (Primary Key)
name
email
Courses

id (Primary Key)
instructor_id (Foreign Key referencing Instructors.id)
name
max_seats
start_date
Leads

id (Primary Key)
course_id (Foreign Key referencing Courses.id)
name
email
phone_number
linkedin_profile
status
Comments

id (Primary Key)
lead_id (Foreign Key referencing Leads.id)
instructor_id (Foreign Key referencing Instructors.id)
comment
created_at
updated_at
Running the Server
Start Server

Run the following command to start the backend server:

Copy code
node server.js
The server will start running on port 34060 by default.

##APIs
Create Course API

Endpoint: POST /api/courses
Request Body: { name, instructor_id, max_seats, start_date }
Update Course Details API

Endpoint: PUT /api/courses/:courseId
Request Body: { name, max_seats, start_date }
Course Registration API

Endpoint: POST /api/courses/:courseId/register
Request Body: { name, email, phone_number, linkedin_profile }
Lead Update API

Endpoint: PUT /api/leads/:leadId
Request Body: { status }
Lead Search API

Endpoint: GET /api/leads?search=name_or_email
Add Comment API

Endpoint: POST /api/comments
Request Body: { lead_id, instructor_id, comment }
Testing
Postman can be used to test the APIs. Set the base URL to http://localhost:34060/api.

##Test data can be manually inserted into the database or generated using Postman requests.

##Conclusion
Follow the provided instructions to set up and run the Airtribe backend server. If you encounter any issues or have questions, feel free to reach out to [your_email@example.com].

##Happy Coding!
