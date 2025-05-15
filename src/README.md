# Mergington High School Activities API

A super simple FastAPI application that allows students to view and sign up for extracurricular activities.

## Features

- View all available extracurricular activities
- Sign up for activities
- Track student portfolios: achievements, leadership roles, and awards

## Getting Started

1. Install the dependencies:

   ```
   pip install fastapi uvicorn
   ```

2. Run the application:

   ```
   python app.py
   ```

3. Open your browser and go to:
   - API documentation: http://localhost:8000/docs
   - Alternative documentation: http://localhost:8000/redoc

## API Endpoints

| Method | Endpoint                                                          | Description                                                         |
| ------ | ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| GET    | `/activities`                                                     | Get all activities with their details and current participant count |
| POST   | `/activities/{activity_name}/signup?email=student@mergington.edu` | Sign up for an activity                                             |
| GET    | `/students/{email}/portfolio`                                     | Get a student's extracurricular portfolio                           |
| POST   | `/students/{email}/portfolio/achievement?achievement=...`         | Add an achievement to a student's portfolio                         |
| POST   | `/students/{email}/portfolio/leadership?role=...`                 | Add a leadership role to a student's portfolio                      |
| POST   | `/students/{email}/portfolio/award?award=...`                     | Add an award to a student's portfolio                               |

## Data Model

The application uses a simple data model with meaningful identifiers:

1. **Activities** - Uses activity name as identifier:

   - Description
   - Schedule
   - Maximum number of participants allowed
   - List of student emails who are signed up

2. **Students** - Uses email as identifier:
   - Name
   - Grade level
   - Portfolio: achievements, leadership roles, awards

All data is stored in memory, which means data will be reset when the server restarts.
