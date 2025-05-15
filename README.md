# 🌍 Visited Countries Tracker

A full-stack Node.js web application that allows users to track the countries they have visited. Built using **Express**, **PostgreSQL**, and **EJS**, this app provides a simple UI to add and visualize visited countries.

## 🚀 Features

- Add a country you've visited using a form.
- Match partial and case-insensitive country names (e.g., `usa` → `United States of America`).
- Store and retrieve visited countries using PostgreSQL.
- Render visited countries and total count on the homepage.
- Handle errors like duplicate entries and invalid country names gracefully.

## 🛠️ Tech Stack

- Backend: Node.js, Express
- Database: PostgreSQL
- Frontend: EJS templates
- Styling: Custom CSS (in `public/`)

##📸 Screenshot
![image](https://github.com/user-attachments/assets/6416cff6-bb5a-4a8b-94ab-16389c0c7c80)


## 🏁 How to Run the App Locally

### 1. Clone the Repository

git clone https://github.com/your-username/visited-countries-tracker.git
cd visited-countries-tracker

2. Install Dependencies
npm install

3. Set Up PostgreSQL
Make sure PostgreSQL is installed and running. Then create a database called World and run the following schema:

CREATE TABLE countries (
  country_name VARCHAR(255),
  country_code VARCHAR(10) PRIMARY KEY
);

CREATE TABLE visited_countries (
  country_code VARCHAR(10) PRIMARY KEY,
  FOREIGN KEY (country_code) REFERENCES countries(country_code)
);
✅ Make sure to fill the countries table with country names and codes.

4. Configure the Database Connection
Update your index.js with your local database credentials:

const db = new pg.Client({
  user: "postgres",
  host: "localhost",
  database: "World",
  password: "your_password",
  port: 5432,
});

6. Start the App
node index.js
Open your browser and go to:
http://localhost:3000

📁 Project Structure
.
├── index.js            # Main server file
├── views/
│   └── index.ejs       # Homepage template
├── public/
│   └── styles.css      # Optional CSS
├── package.json
└── README.md
📌 Future Improvements
Display a world map highlighting visited countries

User authentication for personal lists

Country search autocomplete

📜 License
This project is open-source and available under the MIT License.
