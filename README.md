# Event Management System

A robust, custom-built Event Management System developed using raw PHP with an MVC architecture. This application allows users to register for upcoming events and managers to create and manage them, complete with concurrency protection to prevent double-booking.

![Screenshot](https://github.com/user-attachments/assets/7f209d80-e026-4cee-a771-f747926eb675)

## 🚀 Key Features

*   **Custom MVC Architecture:** Built purely with PHP without heavy frameworks, utilizing a clean Model-View-Controller structure.
*   **User Authentication:** Secure login and registration flows for users to access the platform.
*   **Event Dashboard:** Administrators can create, update, and remove events, specifying name, description, and maximum capacity.
*   **Concurrency Safe Registration:** Utilizes database transactions and pessimistic locking (`FOR UPDATE`) to actively prevent overbooking race-conditions when multiple users attempt to register simultaneously.
*   **Attend Events:** Users can browse available events, view registered attendees versus total capacity, and secure their spots.
*   **Export Attendees:** Integrated CSV export functionality allowing administrators to download lists of registered attendees for specific events.

## 💻 Tech Stack

*   **Backend:** Raw PHP 8.x
*   **Architecture:** MVC (Model-View-Controller)
*   **Database:** MySQL/MariaDB (via PDO)
*   **Environment Configuration:** `vlucas/phpdotenv`
*   **Package Manager:** Composer

## ⚙️ Installation & Setup

Follow these instructions to get the project up and running on your local machine.

### Prerequisites
*   PHP ^8.0
*   MySQL or MariaDB
*   [Composer](https://getcomposer.org/)

### Setup Steps

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/your-username/event-management-system.git
    cd event-management-system
    ```

2.  **Install Dependencies**
    Run Composer to install the required packages (like PHP DotEnv).
    ```bash
    composer install
    ```

3.  **Configure Environment Variables**
    Copy the example environment file and create your local `.env`.
    ```bash
    cp .env.example .env
    ```
    Open the `.env` file and update your database credentials:
    ```env
    DB_HOST=localhost
    DB_NAME=event_management_system
    DB_USER=root
    DB_PASSWORD=your_password
    ```

4.  **Setup Database**
    Create the database specified in your `.env` file (e.g., `event_management_system`) via your database manager (phpMyAdmin, MySQL CLI, etc.).
    Then, import the provided SQL file from the root directory into your database.
    ```bash
    mysql -u root -p event_management_system < event_management_system.sql
    ```

5.  **Serve the Application**
    If using Laravel Valet, Herd, or similar tools, link the project.
    Otherwise, you can serve it via the built-in PHP server depending on how your document root mappings are handled! (Typically served from root directory because of the existing `.htaccess`).
    ```bash
    php -S localhost:8000
    ```

## 🔒 Default Credentials

Once the application is running, you can log in immediately with the pre-seeded admin account:

*   **Email:** `admin@email.com`
*   **Password:** `123456`

> **Note:** For a regular user, simply navigate to the registration page and create a new account!
