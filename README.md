Visited Countries App:
A simple Express.js application that allows users to log countries they have visited and displays them with a color-coded profile. Built with PostgreSQL for data storage and dotenv for environment variable management.

->Features
User Profiles: Users can be created with a specific name and color theme.
Visited Countries Tracking: Users can add countries they have visited, which are then saved in the database and displayed.
Dynamic Content: Displays the total number of visited countries for each user.
Prerequisites
Before you begin, ensure you have the following:

Node.js and npm installed
PostgreSQL installed and running

->Installation
Clone the repository:

bash
git clone https://github.com/jbolan12/Family-Travel-Tracker
cd 'repository_directory'
Install the dependencies:

bash
npm install
Set up the environment variables by creating a .env file with the following content:

->env
Copiar código
DB_USER=your_db_user
DB_HOST=your_db_host
DB_NAME=your_db_name
DB_PASSWORD=your_db_password
DB_PORT=your_db_port

->Database Setup
Connect to your PostgreSQL database:

-Create the users and visited_countries tables:
sql

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    color VARCHAR(50)
);

CREATE TABLE visited_countries (
    id SERIAL PRIMARY KEY,
    user_id INT REFERENCES users(id),
    country_code VARCHAR(3)
);

->Usage
Start the server:

bash
npm start
Visit http://localhost:3000 in your browser.

Routes
GET /: Displays the main page with a list of visited countries for the current user.
POST /add: Adds a new country to the visited list based on user input.
POST /user: Switches the current user or adds a new user.
POST /new: Creates a new user profile.
Deployment
To deploy this application, you can use services like Railway, which supports easy deployment of PostgreSQL-backed applications. Railway also makes environment variable management and database provisioning straightforward, which can be helpful in streamlining deployment.

->Contributing
Feel free to fork this repository and submit pull requests for any improvements.

