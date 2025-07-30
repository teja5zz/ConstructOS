# ConstructOS
ConstructOS, a comprehensive, single-page application (SPA) for construction management.

The application is built using plain HTML, TailwindCSS for styling, and JavaScript, with Firebase (specifically Firestore and Authentication) serving as the backend for data storage and user management.

Core Functionality

The application provides an integrated platform for managing multiple construction projects. Users can have different roles (like Admin, Project Manager, or Site Supervisor), which likely determines their access and permissions within the app.

Key Features:

1. Authentication and User Management

    Users can create an account and log in.

    User data, including their role (e.g., Admin, Project Manager), is stored and retrieved from Firebase.

    A company profile can be created and edited, storing details like company name, GST, and address.

2. Dashboard & Project Navigation

    After logging in, users see a main dashboard with several tabs:

        Activity Feed: Shows all daily progress reports from all projects for the current day.

        Approvals: A centralized view for managers to approve or reject pending material requests and expenses.

        All Parties & Materials: Master lists of all vendors, workers, and materials used across all projects. This allows for centralized tracking.

        Finances & Payroll: Tools to manage company-wide funds (e.g., owner investments) and process monthly payroll for employees, with the ability to attribute costs to specific projects.

        My Projects: A list of all construction projects the user is a member of.

3. Detailed Project View

    Clicking on a project opens a dedicated, tabbed view for managing that specific project:

        Party Tab: Manages all parties (investors, subcontractors, suppliers, workers) related to the project. It calculates and displays the current financial balance (amount to pay or advance paid) for each party.

        Transactions Tab: A complete financial ledger for the project, tracking all incoming and outgoing payments. It includes a dashboard showing the project's total balance, income, and expenses. Users can add various transaction types, such as payments, expenses, and credit/debit notes.

        Site Tab: A daily log view. Users can navigate day-by-day to view stats like staff present, materials received/used, and view/upload site photos and documents. It's also where users create Daily Progress Reports (DPRs).

        Material Tab: A comprehensive material management system with sub-tabs for:

            Inventory: Shows the current stock of all materials on site.

            Request: Allows site supervisors to request materials.

            Received & Used: Logs all incoming materials (with Goods Received Notes) and records daily material consumption.

Technical Implementation

    Single-Page Application (SPA): The entire application runs on a single HTML page. JavaScript is used to dynamically render different views (like the login screen, dashboard, or project view) without needing to reload the page.

    Firebase Backend:

        Authentication: Manages user sign-up, login, and session persistence.

        Firestore Database: A NoSQL database used to store all application data. The data is structured hierarchically under an artifacts collection, separating user-specific data (like master lists) from shared project data.

    Real-time Updates: The application uses Firebase's onSnapshot listeners to update the UI in real-time as data changes in the database (e.g., a new transaction appears instantly for all users viewing that project).

    Modals: Pop-up windows (modals) are used for all data entry forms, such as adding a new project, recording a payment, or creating a material request.
