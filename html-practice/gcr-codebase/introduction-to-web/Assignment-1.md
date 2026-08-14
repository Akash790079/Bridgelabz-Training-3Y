# ASSIGNMENT 1: Introduction to Web Development & Architecture

**Subject:** Web Development Fundamentals  
**Topic:** Frontend, Backend, Web Servers, Browsers & Architecture  

---

### Q1. Explain the difference between frontend, backend, and full-stack development with suitable real-world examples.

**Answer:**

Web development is broadly categorized into three areas:

1. **Frontend Development (Client-Side):**
   - It refers to the user interface (UI) and visual elements of a website that users directly see and interact with in their web browser.
   - **Key Technologies:** HTML, CSS, JavaScript, React, Vue.js.
   - **Real-World Example:** On an e-commerce platform like **Amazon** or **Zomato**, the product catalog grid, search bar, navigation menu, image sliders, and buttons are designed by frontend developers.

2. **Backend Development (Server-Side):**
   - It handles the background operations, business logic, server configurations, API endpoints, and database interactions that are invisible to the user.
   - **Key Technologies:** Node.js, Python (Django/Flask), Java, PHP, MySQL, MongoDB.
   - **Real-World Example:** When you click "Place Order" on Amazon, the backend system processes your payment securely, checks inventory in the database, sends a confirmation SMS/email, and creates an order record.

3. **Full-Stack Development:**
   - It involves working on both frontend and backend aspects of an application. A full-stack developer can build an entire web application end-to-end.
   - **Real-World Example:** Building a personal blog application from scratch — designing the post editor interface (Frontend) as well as setting up the database storage and API routes (Backend).

---

### Q2. Create a simple diagram showing how the client-server model works in web architecture.

**Answer:**

```
                        1. HTTP Request (e.g. GET /index.html)
               +-------------------------------------------------->+
               |                                                   |
     +-------------------+                               +-------------------+
     |      CLIENT       |                               |    WEB SERVER     |
     |   (Web Browser)   |                               |  (Processes Data) |
     +-------------------+                               +-------------------+
               |                                                   |
               +<--------------------------------------------------+
                        2. HTTP Response (HTML / CSS / JS)
```

**Explanation:**
- **Client:** The web browser (like Chrome or Safari) on a smartphone or PC that requests web pages or data.
- **Web Server:** A remote machine hosting website files. It listens for client requests, processes them, and returns the requested resources.

---

### Q3. Describe how a browser requests and displays a web page from a web server.

**Answer:**

When a user enters a URL (e.g., `https://www.example.com`) in the browser address bar, the following steps take place:

1. **DNS Resolution (Domain Name Lookup):** The browser queries a DNS server to convert the human-readable domain (`example.com`) into an IP address (e.g., `93.184.216.34`).
2. **Establishing Connection (TCP Handshake):** The browser initiates a TCP 3-way handshake with the web server (and TLS handshake for HTTPS security).
3. **Sending HTTP Request:** The browser sends an HTTP `GET` request packet asking for the web page content.
4. **Server Response:** The server processes the request and sends back an HTTP status response (`200 OK`) along with the raw HTML, CSS, and JS files.
5. **Parsing HTML & CSS (DOM & CSSOM):** 
   - The browser parses HTML markup to construct the **DOM (Document Object Model)** tree.
   - It parses CSS rules to construct the **CSSOM (CSS Object Model)** tree.
6. **Render Tree & Layout:** DOM and CSSOM are merged to form a Render Tree. The browser calculates element dimensions and positions on screen (Layout/Reflow).
7. **Painting:** The browser rasterizes and paints pixels onto the display screen to render the final web page.

---

### Q4. Identify and list the tools required to set up a web development environment. Explain the purpose of each.

**Answer:**

The primary tools required for setting up a modern web development environment are:

1. **Code Editor / IDE (e.g., Visual Studio Code):**
   - **Purpose:** Used to write, edit, format, and organize HTML, CSS, and JavaScript source code cleanly.
2. **Web Browser with DevTools (e.g., Google Chrome / Mozilla Firefox):**
   - **Purpose:** Used to view rendered web pages and use Developer Tools (F12) to inspect DOM elements, debug JavaScript errors, and monitor network requests.
3. **Version Control System (e.g., Git & GitHub):**
   - **Purpose:** Tracks code history, manages different code branches, creates backups, and allows team collaboration.
4. **Runtime Environment & Package Manager (e.g., Node.js & npm):**
   - **Purpose:** Node.js executes JavaScript on the local machine outside the browser, while npm installs third-party libraries and tools.
5. **Terminal / Command Line Interface (CLI):**
   - **Purpose:** Used to execute build commands, start local development servers, and run Git commands.

---

### Q5. Explain what a web server is and give examples of commonly used servers.

**Answer:**

- **Web Server Definition:** A web server is a combination of computer hardware and software that stores website assets (HTML documents, CSS files, images, JavaScript files) and delivers them to client devices across the Internet via the **HTTP/HTTPS** protocol.

**Examples of Commonly Used Web Servers:**
1. **Apache HTTP Server:** A widely used, modular open-source web server.
2. **NGINX:** A high-performance web server known for reverse proxying and handling heavy concurrent traffic.
3. **Microsoft IIS (Internet Information Services):** A web server designed for Windows Server environments.
4. **LiteSpeed:** A high-speed commercial web server optimized for performance.
5. **Caddy:** A modern open-source web server written in Go with automatic HTTPS configuration.

---

### Q6. Define the roles of a frontend developer, backend developer, and database administrator in a project.

**Answer:**

1. **Frontend Developer:**
   - **Role:** Focuses on user interface (UI) and user experience (UX).
   - **Tasks:** Translates design wireframes into responsive HTML/CSS code, handles client-side form validations, and integrates APIs for dynamic data display.

2. **Backend Developer:**
   - **Role:** Focuses on server-side architecture and business logic.
   - **Tasks:** Writes REST/GraphQL APIs, handles database queries, implements user authentication (login/signup security), and manages server configuration.

3. **Database Administrator (DBA):**
   - **Role:** Focuses on data storage, integrity, and performance.
   - **Tasks:** Designs database schemas and tables, writes optimized SQL queries, manages user permissions, creates routine backups, and ensures high availability.

---

### Q7. Install VS Code and configure it for HTML, CSS, and JavaScript development. Take a screenshot of the setup.

**Answer:**

**Setup Instructions:**
1. Download VS Code from [code.visualstudio.com](https://code.visualstudio.com/) and run the installer.
2. Launch VS Code and open project directory via **File > Open Folder**.
3. Create project structure:
   - `index.html` (HTML structure)
   - `style.css` (Styles)
   - `script.js` (JavaScript logic)
4. **Install Essential Extensions:**
   - **Live Server:** Right-click HTML file to open local live-reloading server.
   - **Prettier - Code Formatter:** Auto-formats code on save.
   - **HTML CSS Support:** Auto-completes CSS class names in HTML files.

**Project Folder Setup:**
```
my-first-web-project/
│── index.html
│── style.css
└── script.js
```

---

### Q8. Explain the difference between static and dynamic websites. Provide an example of each.

**Answer:**

| Parameter | Static Website | Dynamic Website |
| :--- | :--- | :--- |
| **Content** | Fixed HTML content, identical for every visitor. | Content is generated dynamically based on user actions and database records. |
| **Database** | Does not require a database. | Requires a database (SQL/NoSQL) to store and retrieve data. |
| **Speed & Hosting** | Loads very fast and cheap to host. | Requires server processing time and backend infrastructure. |
| **Example** | A company portfolio website or static documentation page. | YouTube, Facebook, Netflix, or Amazon. |

---

### Q9. Research and list five web browsers. Explain how rendering engines differ between them.

**Answer:**

**Five Popular Web Browsers & Engines:**
1. **Google Chrome** — Rendering Engine: **Blink** (JavaScript Engine: V8)
2. **Mozilla Firefox** — Rendering Engine: **Gecko** (JavaScript Engine: SpiderMonkey)
3. **Apple Safari** — Rendering Engine: **WebKit** (JavaScript Engine: JavaScriptCore)
4. **Microsoft Edge** — Rendering Engine: **Blink** (Chromium-based)
5. **Brave Browser** — Rendering Engine: **Blink** (Chromium-based)

**Key Differences Between Rendering Engines:**
- A rendering engine takes HTML, CSS, and image files and renders them onto the screen.
- **Blink** and **WebKit** focus on multi-threaded performance and rapid standard adoption.
- **Gecko** (Firefox) uses a parallel CSS rendering architecture written in Rust (WebRender/Quantum) for smooth layout calculations.
- Different rendering engines interpret CSS specs and layout rules with minor variations.

---

### Q10. Draw a labeled diagram showing the basic web architecture flow — client, server, database, and APIs.

**Answer:**

**Web Architecture Flow Diagram:**

```
+-------------------+        1. HTTP/API Request       +-------------------+        3. Database Query      +-------------------+
|   CLIENT LAYER    | -------------------------------> |   SERVER LAYER    | ---------------------------> |  DATABASE LAYER   |
|  (Browser / App)  |                                  |  (Node.js / API)  |                              |  (MySQL / Mongo)  |
|                   | <------------------------------- |                   | <--------------------------- |                   |
+-------------------+         4. JSON Response         +-------------------+        2. Data Records       +-------------------+
```

**Architecture Flow Steps:**
1. **Client (Frontend):** User performs an action (e.g. submitting a form) in the web browser.
2. **API Request:** Browser sends an HTTP request payload (JSON) to the backend API endpoint.
3. **Server Logic:** Backend server validates the request, runs business rules, and queries the database.
4. **Database:** Database processes the SQL/NoSQL query and returns requested records to the server.
5. **API Response:** Server formats data as JSON and sends HTTP response back to the client to render on screen.
