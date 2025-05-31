
# Task Managment Application

## Task Management App (front-end)
The frontend code is organized in a Next.js project structure with TypeScript, React, and shad-cn UI libraries. Below is the proposed folder structure for the frontend repository:

## Live App

You can access the live Task Management Application at https://arm-assessment-front-k6x3p.ondigitalocean.app/. Log in using the credentials:
- **Email**: ```demo@demo.com```
- **Password**: ```demo123```
## Screenshots
- <video src="https://github.com/user-attachments/assets/8b6ca3a4-e5e0-44b0-b93c-9553de86b2bd" />
<img width="1437" alt="Screenshot 2025-05-31 at 8 06 16 AM" src="https://github.com/user-attachments/assets/114b4de1-285d-4c51-9ffc-a3e3f05c4d43" />
<img width="721" alt="Screenshot 2025-05-31 at 8 07 20 AM" src="https://github.com/user-attachments/assets/31ba4351-a3b8-4966-80ea-d21dfd90cc0a" />
<img width="1423" alt="Screenshot 2025-05-31 at 8 07 54 AM" src="https://github.com/user-attachments/assets/9678589e-e203-4c63-a3a2-2a1f0a8a1b05" />
<img width="400" src="https://github.com/user-attachments/assets/7506afe6-a34b-41fb-98be-75c583f3bfc5" />
<img width="400" src="https://github.com/user-attachments/assets/849072c1-4f60-4747-982f-ccc82535e0da" />
<img width="400" src="https://github.com/user-attachments/assets/93467654-0433-40e9-ab85-3b4b837ba68f" />
<img width="400" src="https://github.com/user-attachments/assets/f3724501-fc6d-4d84-837f-04d57f9cbe59" />
<img width="400" src="https://github.com/user-attachments/assets/56b666dd-96a3-4e5e-85db-e295ff817762" />
<img width="400" src="https://github.com/user-attachments/assets/ea96cf99-b424-4ade-b4c9-a81b031c729c" />
<img width="400" src="https://github.com/user-attachments/assets/bfda1774-f396-4d7a-bf99-b308905e243a" />


## Features
- **Task Management**: Create, edit, delete, and move tasks across status or priority columns.
- **Drag-and-Drop**: Reorder tasks using `react-dnd` with support for both mouse and touch inputs.
- **Responsive Design**: Adapts to mobile and desktop devices using the `useDeviceMode` hook.
- **Authentication**: Integrated with Supabase for user authentication and session management.
- **Task Filtering**: Filter tasks by category, status, priority, and date range.
- **Data Visualization**: Displays task statistics with bar charts using `recharts`.
- **UI Components**: Uses Shadcn UI for accessible and customizable components.

## Prerequisites
- Node.js (v18 or higher)
- npm or Yarn
- Supabase account and project
- Backend API (see backend repository for details)

## Setup Instructions
1. **Clone the Repository**
   ```bash
   git clone https://github.com/rimney/Arm-Assessment.git TaskApp
   cd Arm-Assessment
2. **Install Dependencies**
   ```bash
    npm install
    # or 
    yarn install
3. **Configure Environment Variables** Create a ```.env.local``` file in the root directory and add the following:
    ```
    NEXT_PUBLIC_SUPABASE_URL=your-supabase-url
    NEXT_PUBLIC_SUPABASE_ANON_KEY=your-supabase-anon-key
    NEXT_PUBLIC_API_URL=your-backend-api-url
    ```
4. **Run the Development Server**
    ```
    npm run dev
    # or
    yarn dev
    ```
Open ```http://localhost:3000``` in your browser.

5. **Build for Production**
    ```

    npm run build

    npm run start
    # or
    yarn build
  
    yarn start  
    
## Dependencies

- ```next```: Next.js framework for server-side rendering and static site generation.
- ```react```, react-dom: Core React libraries.
- ```react-dnd```, react-dnd-html5-backend, react-dnd-touch-backend, react-dnd-multi-backend: For drag-and-drop functionality.
- ```recharts```: For rendering bar charts.
- ```@supabase/supabase-js```: Supabase client for authentication.
- ```axios```: For making HTTP requests to the backend API.
- ```sonner```: For toast notifications.
- ```lucide-react```: For icons.
- ```react-day-picker```: For date range picker.
- ```date-fns```: For date formatting.
- ```typescript```: For type safety.
- ```Shadcn UI components```: button, card, dialog, sheet, tabs, etc.

## Running the App

- Ensure the backend API is running (see backend section for setup or docker-compose section to build and run the app at once).
- Log in using Supabase authentication to access the dashboard.
- Use the "Tasks" tab to manage tasks or the "Dashboard" tab to view statistics.
## Notes

- The drag-and-drop feature is optimized for both desktop and mobile devices.
- Task filters are reactive and update the displayed tasks in real-time.

### Explanation of Implementation Decisions

1. **Next.js and TypeScript**:
   - **Why**: Next.js was chosen for its server-side rendering, static site generation, and built-in routing, which improve performance and SEO. TypeScript ensures type safety, reducing runtime errors and improving developer experience.
   - **Impact**: Provides a robust foundation for scalability and maintainability.

2. **Supabase for Authentication**:
   - **Why**: Supabase provides a simple and secure authentication system with a JavaScript client, making it easy to integrate with the frontend. The `useAuth` hook handles session management and redirects unauthenticated users to the login page.
   - **Impact**: Simplifies user authentication and integrates seamlessly with the backend.

3. **Drag-and-Drop with `react-dnd`**:
   - **Why**: `react-dnd` with `react-dnd-multi-backend` supports both HTML5 (mouse) and touch (mobile) inputs, ensuring cross-device compatibility. The `DragLayer` component enhances the drag experience with smooth scrolling and visual feedback.
   - **Impact**: Enables intuitive task reordering with a responsive UX.

4. **Responsive Design with `useDeviceMode`**:
   - **Why**: The `useDeviceMode` hook detects mobile vs. desktop devices, allowing conditional rendering (e.g., `Sheet` for mobile, `Dialog` for desktop) and layout adjustments.
   - **Impact**: Ensures a consistent and user-friendly experience across devices.

5. **Shadcn UI Components**:
   - **Why**: Shadcn UI provides accessible, customizable, and lightweight components that integrate well with Tailwind CSS, reducing the need for custom CSS while maintaining a consistent design.
   - **Impact**: Speeds up development and ensures accessibility compliance.

6. **Task Filtering and Visualization**:
   - **Why**: The `TaskFilters` component allows dynamic filtering by category, status, priority, and date range, improving usability. `TaskCharts` uses `recharts` to visualize task distribution by status and category, providing actionable insights.
   - **Impact**: Enhances user interaction and data analysis.

7. **Color Scheme and Styling**:
   - **Why**: A dark theme with `#CAFE14` (green) as the primary accent color was chosen for visual appeal and readability. Custom styles for components like `DayPicker` ensure consistency.
   - **Impact**: Creates a cohesive and modern UI.

8. **Axios with Authentication**:
   - **Why**: The `useAxiosAuth` hook adds Supabase access tokens to API requests, ensuring secure communication with the backend.
   - **Impact**: Simplifies API integration and maintains security.

## Task Management App (Backend)
This is the backend of a task management application built with NestJS, TypeScript, Prisma, and Supabase for authentication. It provides RESTful APIs for managing tasks and integrates with a PostgreSQL database.

## Features
- **Task Management**: CRUD operations for tasks (create, read, update, delete).
- **Authentication**: JWT-based authentication using Supabase.
- **Database**: PostgreSQL with Prisma ORM for type-safe database interactions.
- **Validation**: DTOs with `class-validator` for input validation.
- **Error Handling**: Robust error handling for database and API operations.
- **CORS**: Configured to allow requests from the frontend.


## Prerequisites
- Node.js (v18 or higher)
- npm or Yarn
- PostgreSQL database
- Supabase account and project
- Frontend application (see frontend repository for details)

## Setup Instructions

1. **Install Dependencies**
   ```bash
    npm install
    # or
    yarn install
2. **Configure Environment Variables** Create a ```.env``` file in the root directory and add the following:
   ```env
   DATABASE_URL=postgresql://<username>:<password>@<host>:<port>/<database>?schema=public
   SUPABASE_JWT_SECRET=your-supabase-jwt-secret
3. **Set Up the Database**
- Ensure PostgreSQL is running.
- Run Prisma migrations to set up the database schema:
   ```bash
   npx prisma migrate dev --name init
4. **Run the Development Server**
   ```bash
   npm run start:dev
   # or 
   yarn start:dev
- The server will run on ```http://localhost:8081```.
5. **Build for Production**
   ```bash
    npm run build
    npm run start:prod
    # or
    yarn build
    yarn start:prod
## API Endpoints
- ```GET /```: Returns a simple greeting.
- ```GET /protected```: Protected endpoint returning authenticated user details (requires JWT).
- ```POST /tasks```: Create a new task.
- ```GET /tasks```: Retrieve all tasks.
- ```GET /tasks/:id```: Retrieve a task by ID.
- ```PATCH /tasks/:id```: Update a task by ID.
- ```DELETE /tasks/:id```: Delete a task by ID.

## Dependencies

- ```@nestjs/core```, @nestjs/common: NestJS framework.
- ```@nestjs/config```: For environment variable management.
- ```@nestjs/passport```, passport-jwt: For JWT authentication.
- ```@prisma/client```: Prisma ORM for database interactions.
- ```class-validator```, class-transformer: For DTO validation and transformation.
- ```cors```: For enabling CORS.
## Project Structure

- ```src/auth/```: Authentication modules, guards, and strategies.
- ```src/prisma/```: Prisma service and module for database access.
- ```src/tasks/```: Task-related controllers, services, and DTOs.
- ```prisma/```: Prisma schema and migrations.
- ```.env```: Environment variables.
- ```package.json```: Dependencies and scripts.

## Running the App

- Ensure the PostgreSQL database is running and migrated.
- Ensure the frontend is configured to communicate with http://localhost:8081.
- Use Supabase for user authentication to generate JWTs for API requests.

## Notes

- The backend uses a PostgreSQL database with a tasks table defined in schema.prisma.
- Supabase JWTs are validated using the SUPABASE_JWT_SECRET environment variable.
- Input validation ensures API requests with proper error messages.

## Explanation of Implementation Decisions

1. **NestJS and TypeScript**:
   - **Why**: NestJS provides a modular, scalable architecture with dependency injection, making it ideal for building RESTful APIs. TypeScript ensures type safety and improves maintainability.
   - **Impact**: Simplifies development and supports future scalability.

2. **Prisma ORM**:
   - **Why**: Prisma offers type-safe database access, schema migrations, and a clean API for PostgreSQL. The `schema.prisma` file defines the `tasks` model with enums for `Priority`, `Status`, and `Category`.
   - **Impact**: Reduces boilerplate code and ensures database consistency.

3. **Supabase for Authentication**:
   - **Why**: Supabase provides a secure JWT-based authentication system. The `SupabaseStrategy` validates JWTs, and `JwtAuthGuard` protects sensitive routes like `/protected`.
   - **Impact**: Simplifies authentication integration with the frontend and ensures secure API access.

4. **DTOs with Validation**:
   - **Why**: `CreateTaskDto` and `UpdateTaskDto` use `class-validator` to enforce data integrity (e.g., required fields, valid date strings). The `ValidationPipe` strips invalid properties and transforms payloads.
   - **Impact**: Prevents invalid data from reaching the database and improves API reliability.

5. **Error Handling**:
   - **Why**: The `TasksService` handles Prisma errors (e.g., `P2002` for conflicts, `P2003` for constraint violations) and throws meaningful exceptions (`NotFoundException`, `ConflictException`).
   - **Impact**: Provides clear feedback to the frontend and improves debugging.

6. **CORS Configuration**:
   - **Why**: CORS is enabled with `app.enableCors` to allow requests from the frontend (e.g., `http://localhost:3000`). The configuration allows all origins for development simplicity.
   - **Impact**: Ensures seamless frontend-backend communication.

7. **RESTful API Design**:
   - **Why**: Standard REST endpoints (`GET`, `POST`, `PATCH`, `DELETE`) are implemented for task management, following best practices for simplicity and clarity.
   - **Impact**: Makes the API intuitive and easy to integrate with the frontend.

8. **Database Schema**:
   - **Why**: The `tasks` model uses enums for `Priority`, `Status`, and `Category` to enforce valid values. The `description` field is stored as JSON to accommodate structured data (summary, details, acceptance criteria, notes).
   - **Impact**: Provides flexibility for task metadata while maintaining type safety.

## Docker Compose

This section explains how to run the entire Task Management Application (front-end, back-end, and PostgreSQL database) using a single ```docker-compose``` command. The setup uses Docker Compose to orchestrate the Next.js front-end, NestJS back-end, and PostgreSQL database, with the database initialized using a ```dump.sql``` file.

### Prerequisites

- Docker and Docker Compose installed on your machine.
- Node.js (v18 or higher) for local dependency installation (optional for Docker setup).
- The dump.sql file in the project root (TaskApp/) or back-end/ directory, containing the initial database schema and data.

### Setup Instructions

1. **Clone the Repositories** Ensure both the front-end and back-end repositories are cloned into a single project directory (e.g., ```TaskApp/```):
   ``` bash
      mkdir TaskApp
      cd TaskApp
      git clone https://github.com/rimney/Arm-Assessment.git TaskApp
2. **Verify Directory Structure** The project should have the following structure:
   ```
   TaskApp/
   ├── docker-compose.yml
   ├── dump.sql
   ├── front-end/
   │   ├── Dockerfile.dev
   │   ├── app/
   │   ├── components/
   │   ├── package.json
   │   ├── ...
   ├── back-end/
   │   ├── Dockerfile.dev
   │   ├── prisma/
   │   ├── src/
   │   ├── package.json
   │   ├── ...

3. **Run Docker Compose** Build and start all services (front-end, back-end, and database) with: 
   ```
   docker-compose up --build
- This command :
   - Builds the frontend and backend services using front-end/Dockerfile.dev and back-end/Dockerfile.dev.
   - Starts the PostgreSQL database, initializing it with dump.sql.
   - Sets up the network (app-network) for communication between services.
   - Uses environment variables for Supabase and database connections.
4. **Access the Application** Once the services are running (you’ll see logs in the terminal), access:
- **Front-end**: Open http://localhost:3000 in your browser to use the Task Management App (log in via Supabase authentication).
- **Back-end API:** Test API endpoints at http://localhost:8081 + Bearer ${TOKEN} (e.g., http://localhost:8081/tasks  + Bearer ${TOKEN} for task management).
- **Database:** : Connect to localhost:5439 using a PostgreSQL client (e.g., pgAdmin) with:
   - User: ```admin```
   - Password: ```password```
   - Database: ```taskdb```
5. **Stop the Application :** To stop the services, press Ctrl+C in the terminal, then clean up:
   ```
   docker-compose down
To also reset the database (clear dump.sql data):
   ```
   docker-compose down -v
   ```
### Notes

- **dump.sql**: The dump.sql file in TaskApp/ initializes the taskdb database. Ensure it contains valid PostgreSQL commands compatible with Prisma’s schema.prisma.
- **Ports**: The app uses:
   - **Front-end**: 3000
   - **Back-end**: 8081
   - **Database**: 5439 If these ports are in use, update the ports in docker-compose.yml (e.g., change "5439:5432" to "5440:5432" for the database).
- **Prisma Migrations**: If dump.sql doesn’t fully align with schema.prisma, run Prisma migrations after starting the services:
   ```
   docker-compose run backend npx prisma migrate dev
   ```
- **Supabase:** The app uses an external Supabase instance for authentication. Ensure internet access.
