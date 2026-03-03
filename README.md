React Authentication and API Practice
This project is a React application designed to demonstrate a secure login flow, route protection, and data fetching from an external API.

Project Overview
The application allows users to log in using specific credentials. Once authenticated, they gain access to a protected Dashboard that fetches and displays data from the JSONPlaceholder API. If a user is not logged in, they are restricted from viewing the Dashboard.

How to Run the Program
Clone this repository to your local machine.
Open your terminal or command prompt.

Navigate into the project folder:
cd your-project-name

Install the necessary dependencies:
npm install

Start the application:
npm start

The app will open automatically in your browser at http://localhost:3000.

Test Credentials
To access the protected dashboard, use the following credentials:

Username: admin
Password: password123

Technical Implementation & Decisions
Below are the answers to the core technical requirements of this task:

1. Component Structure
The application is structured into a main App component that handles routing. I separated the logic into a "pages" folder for the Login and Dashboard views, and a "components" folder for reusable logic like the Protected Route. This keeps the code organized and easy to scale.

2. State Management
I chose to lift the authentication state to the top-level App component. By managing the "isAuthenticated" status in App.js, I can easily pass that information down to both the Login page (to update it) and the Protected Route (to check it).

3. Protected Route in React Router
To secure the Dashboard, I implemented a ProtectedRoute component. This component checks the authentication state; if the user is logged in, it renders the Dashboard. If not, it uses the "Navigate" component from React Router to redirect the user back to the Login page automatically.

4. App Appearance (Layout, Colors, and Spacing)
I focused on a clean, professional UI using standard CSS. I used Flexbox to center the login card and ensure the dashboard layout is responsive. I chose a high-contrast color scheme (blue and white) for buttons to ensure clear calls to action, with consistent padding and margins for better readability.

5. Loading and Error States for API Calls
When fetching data for the Dashboard, I implemented three distinct states:

Loading: A message is displayed while the data is being fetched.
Success: The data is mapped and displayed in a list once received.
Error: A catch block handles network failures or API issues, displaying a friendly error message to the user so they aren't left with a blank screen.

Challenges and Learnings       
Understanding how to prevent unauthorized access to specific URLs.
Learning to manage multiple states (loading vs. error) during an API call.
Ensuring the UI remains stable while waiting for asynchronous data.
