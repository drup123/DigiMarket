# DigiMarket: A Farmer-to-Consumer Marketplace

DigiMarket is a full-stack web application built using **Advanced Java (JSP, Servlets, and JDBC)**. It serves as a digital portal that directly connects farmers with buyers, removing the need for traditional middlemen.

This platform empowers farmers to post their produce for sale and allows consumers to browse and purchase fresh goods directly, creating a more transparent and efficient agricultural supply chain.

## ✨ Features

The application is built with three distinct user roles, each with its own secure portal and functionalities:

### 1. 🧑‍⚖️ Admin
* **User Management:** Full CRUD (Create, Read, Update, Delete) capabilities for all farmer accounts.
* **Buyer Oversight:** Ability to view the list of all registered buyers.
* **Product Management:** Can manage all product listings on the platform.

### 2. 👩‍🌾 Farmer
* **Authentication:** Secure registration and login.
* **Product Management:** Can post their products for sale, including details like name, quantity, and price.
* **Order Management:** Can view and manage all incoming orders for their products.
* **Profile:** Can change their password.

### 3. 🧑‍🛒 Buyer
* **Authentication:** Secure registration and login.
* **Browse & Purchase:** Can browse all available products from all farmers and place orders.
* **Order Tracking:** Has a personal dashboard to track the status of all their placed orders.
* **Profile:** Can change their password.

## 💻 Tech Stack

This project was built from scratch using a core Java EE stack:

* **Backend (Controller):** **Java Servlets** (to handle all business logic, routing, and session management).
* **Frontend (View):** **JSP (JavaServer Pages)** (to dynamically render all web pages with data from the server).
* **Database:** **MySQL** (for all data storage).
* **Database Connectivity:** **JDBC (Java Database Connectivity)** (for all communication between the servlets and the MySQL database).
* **Web Server:** **Apache Tomcat** (the server container to run the application).
* **Frontend Design:** **HTML, CSS** (for layout and styling).

## 🚀 Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

You will need the following software installed on your machine:
* [Java JDK](https://www.oracle.com/java/technologies/downloads/) (Version 8 or newer)
* [Apache Tomcat](https://tomcat.apache.org/) (Version 9 or newer)
* [MySQL Server](https://dev.mysql.com/downloads/mysql/)
* An IDE like [Eclipse IDE for Java EE Developers](https://www.eclipse.org/downloads/packages/) or [IntelliJ IDEA Ultimate](https://www.jetbrains.com/idea/)

### Installation

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/drup123/DigiMarket.git](https://github.com/drup123/DigiMarket.git)
    ```

2.  **Set up the Database:**
    * Open your Xampp/workbench.
    * Create a new database (e.g., `digimarket_db`).
    * Run the following SQL scripts to create the necessary tables:

    ```sql
    CREATE TABLE farmer (
        id INT NOT NULL AUTO_INCREMENT,
        name VARCHAR(100),
        location VARCHAR(255),
        contact VARCHAR(15),
        email VARCHAR(100) UNIQUE,
        password VARCHAR(100),
        PRIMARY KEY (id)
    );

    CREATE TABLE buyer (
        id INT NOT NULL AUTO_INCREMENT,
        name VARCHAR(100),
        contact VARCHAR(15),
        address TEXT,
        email VARCHAR(100) UNIQUE,
        password VARCHAR(100),
        PRIMARY KEY (id)
    );

    CREATE TABLE products (
        id INT NOT NULL AUTO_INCREMENT,
        farmerId INT,
        productName VARCHAR(100),
        quantity VARCHAR(50),
        price DECIMAL(10, 2),
        postDate DATE,
        PRIMARY KEY (id),
        FOREIGN KEY (farmerId) REFERENCES farmer(id)
    );

    CREATE TABLE orders (
        id INT NOT NULL AUTO_INCREMENT,
        buyerId INT,
        productId INT,
        quantity VARCHAR(50),
        totalAmount DECIMAL(10, 2),
        orderDate DATE,
        status VARCHAR(50),
        PRIMARY KEY (id),
        FOREIGN KEY (buyerId) REFERENCES buyer(id),
        FOREIGN KEY (productId) REFERENCES products(id)
    );
    ```

3.  **Configure JDBC Connection:**
    * Open the project in your IDE.
    * Find the Java file that handles the database connection (`DBconnection.java` file).
    * Update the JDBC URL, username, and password to match your MySQL database setup.
    `String url = "jdbc:mysql://localhost:3306/digimarket_db";`
    `String username = "your_mysql_username";`
    `String password = "your_mysql_password";`

4.  **Run the Application:**
    * Add your Apache Tomcat server to your IDE's server runtime configuration.
    * Right-click the project and choose "Run As" > "Run on Server".
    * Select your Tomcat server and click Finish.
    * The application will build and deploy. It should automatically open in your browser.

5.  **Access the Portal:**
    You can access the application at `http://localhost:8080/DigiMarket/`.

## 📸 Screenshots

<img width="1919" height="869" alt="Screenshot 2025-11-05 145240" src="https://github.com/user-attachments/assets/0b7dbc97-94d1-42ff-a839-799fd8136d2e" />
<img width="1919" height="869" alt="Screenshot 2025-11-05 145320" src="https://github.com/user-attachments/assets/ab835e08-eb71-4f40-a5f6-cc12716770b5" />
<img width="1919" height="867" alt="Screenshot 2025-11-05 145516" src="https://github.com/user-attachments/assets/3be52156-8357-48c9-9668-f41734e0e64c" />
<img width="1918" height="864" alt="Screenshot 2025-11-05 145537" src="https://github.com/user-attachments/assets/babe3455-fff9-476a-a1e8-d72e61f3085d" />
<img width="1917" height="865" alt="Screenshot 2025-11-05 145706" src="https://github.com/user-attachments/assets/846bb8fd-1e7a-4b2b-a658-ece2baced585" />
<img width="1917" height="873" alt="Screenshot 2025-11-05 145803" src="https://github.com/user-attachments/assets/2ee5db2d-d7d6-45b3-a6b8-90178a1b93b4" />
<img width="1919" height="864" alt="Screenshot 2025-11-05 145826" src="https://github.com/user-attachments/assets/435caeac-7488-4be3-8b98-fcd5080551df" />


## 👤 Connect with Me

* **Drup Patil**
    * LinkedIn: [www.linkedin.com/in/drup-patil-3609b5296](https://www.linkedin.com/in/drup-patil-3609b5296/)
    * GitHub: [https://github.com/drup123](https://github.com/drup123)
