# Assignment 1 Solutions: Web Architecture & Development Fundamentals

---

## Question 1: Difference between Frontend, Backend, and Full-Stack Development

| Feature | Frontend Development | Backend Development | Full-Stack Development |
| :--- | :--- | :--- | :--- |
| **Definition** | Development of the client-side UI and user interaction layer. | Development of server-side logic, database interactions, and business logic. | Combination of both frontend (client-side) and backend (server-side) development. |
| **Key Technologies** | HTML, CSS, JavaScript, React, Vue, Angular, Tailwind CSS | Node.js, Python (Django/FastAPI), Java, PHP, Go, PostgreSQL, MongoDB | HTML/CSS/JS + Node.js/Python + SQL/NoSQL + Git + DevOps basics |
| **Focus** | User Experience (UX), Visual Design, Responsiveness, Accessibility | Data processing, Security, Server performance, API endpoints, Authentication | End-to-end application architecture, integration between UI and server data |
| **Execution Location** | User's Web Browser | Remote Web Server / Cloud Server | Executed across both Browser and Server |

### Real-World Examples:
1. **Frontend Example**: On an e-commerce store like **Amazon**, everything you see—the product cards, navigation bar, image gallery carousel, search filter buttons, and CSS animations—is built by frontend developers.
2. **Backend Example**: When you click **"Buy Now"**, the system securely processes your credit card details, checks warehouse database inventory, updates order status, and triggers a confirmation email. This is handled by backend developers.
3. **Full-Stack Example**: A developer who creates a custom blog feature—building the UI form where users write posts (Frontend), writing the REST API endpoint that receives the post content, saving it to a PostgreSQL database (Backend), and deploying the feature—is working as a Full-Stack developer.

---

## Question 2: Client-Server Model Diagram & Explanation

### Diagram:
```
  +-----------------------+                         +-----------------------+
  |    CLIENT (Browser)   |                         |       WEB SERVER      |
  |                       |                         |                       |
  |  - User UI            |   1. HTTP Request       |  - Processes request  |
  |  - Sends HTTP Requests| ----------------------> |  - Runs backend logic |
  |  - Renders HTML/CSS/JS| <---------------------- |  - Fetches data       |
  |                       |   2. HTTP Response      |                       |
  +-----------------------+   (HTML, CSS, JSON)     +-----------------------+
```

### Explanation:
- **Client (Request Initiator)**: Represents the device or web browser (e.g., Chrome) that requests information or services.
- **HTTP Request**: The client sends a request message over the network using protocols like HTTP/HTTPS (e.g., `GET /index.html`).
- **Web Server (Response Provider)**: Accepts the incoming request, processes it (executes scripts or fetches files), and generates a response.
- **HTTP Response**: The server sends back the requested resource along with an HTTP status code (e.g., `200 OK` + HTML content).

---

## Question 3: How a Browser Requests and Displays a Web Page

The step-by-step process from typing a URL to seeing the final web page:

```
[1. Enter URL] ---> [2. DNS Lookup] ---> [3. TCP / TLS Handshake] ---> [4. HTTP Request]
                                                                                |
[7. Paint Page] <--- [6. Render Tree] <--- [5. Parse HTML/CSS] <--- [Server Sends Response]
```

1. **URL Parsing & DNS Resolution**:
   - The user enters `https://example.com` into the address bar.
   - The browser parses the domain name and checks its local DNS cache. If not found, it queries a DNS server to resolve `example.com` to its corresponding IP address (e.g., `193.0.2.1`).

2. **TCP Connection & TLS Handshake**:
   - The browser establishes a TCP connection with the server via a **3-way handshake** (SYN -> SYN-ACK -> ACK).
   - If HTTPS is used, an SSL/TLS handshake occurs to encrypt the communication channel.

3. **Sending HTTP GET Request**:
   - The browser sends an HTTP `GET` request packet asking for the web page resources (HTML document, CSS stylesheets, images, JS files).

4. **Server Processing & Response**:
   - The web server receives the request, locates the requested index file or runs server code, and responds with an HTTP status code (e.g., `200 OK`) and the raw HTML body.

5. **Parsing & Construction (DOM & CSSOM)**:
   - **DOM Construction**: The browser engine parses raw HTML bytes into HTML tokens and builds the **Document Object Model (DOM)** tree.
   - **CSSOM Construction**: The browser fetches linked CSS files and builds the **CSS Object Model (CSSOM)** tree.

6. **Render Tree, Layout & Painting**:
   - **Render Tree**: The DOM and CSSOM are combined into a Render Tree containing only visible nodes.
   - **Layout (Reflow)**: The browser calculates exact layout coordinates and geometry for each element.
   - **Painting**: The engine rasterizes pixel data onto the screen to render the final visual output.

---

## Question 4: Web Development Environment Tools

| Tool Category | Tool Example | Purpose / Function |
| :--- | :--- | :--- |
| **Code Editor / IDE** | **VS Code** (Visual Studio Code) | Primary environment for writing code. Provides syntax highlighting, auto-completion (IntelliSense), extensions, git integration, and debugging. |
| **Web Browser** | **Google Chrome / Firefox** | Used to run and test web applications. DevTools allow developers to inspect DOM elements, edit CSS live, debug JS code, and analyze network performance. |
| **Version Control System** | **Git & GitHub** | Tracks code modifications, enables branching, allows rolling back changes, and facilitates collaborative team development. |
| **Runtime & Package Manager** | **Node.js & npm** | Node.js executes JavaScript on the local machine outside the browser. npm manages and installs external packages and libraries (e.g., Express, React). |
| **Command Line Interface** | **Terminal / PowerShell** | Executes development commands, runs build scripts, operates git commands, starts local development servers, and manages project files. |

---

## Question 5: What is a Web Server & Commonly Used Examples

### Definition:
A **Web Server** refers to both hardware (a computer connected to the internet) and software that stores website content (HTML files, images, stylesheets, scripts) and serves it over the World Wide Web using client-server protocols like **HTTP** and **HTTPS**.

When a client sends a request via a browser, the web server processes the request, locates the required file or runs dynamic code scripts, and returns the response payload back to the client.

### Commonly Used Web Servers:
1. **Apache HTTP Server**: Open-source, modular, highly configurable web server widely used across platforms.
2. **NGINX**: High-performance, lightweight web server and reverse proxy known for handling high concurrency and asynchronous event handling.
3. **Microsoft IIS (Internet Information Services)**: Windows-native web server integrated with .NET technologies.
4. **Caddy**: Modern open-source web server written in Go that automatically handles HTTPS certificate renewal via Let's Encrypt.
5. **LiteSpeed**: High-performance proprietary web server offering compatibility with Apache configurations and built-in caching engine.

---

## Question 6: Roles of Frontend Developer, Backend Developer, and Database Administrator

```
                  +-------------------------------------------------+
                  |                   PROJECT TEAM                  |
                  +-----------------------+-------------------------+
                                          |
        +---------------------------------+---------------------------------+
        |                                 |                                 |
+-------v-------+                 +-------v-------+                 +-------v-------+
|   FRONTEND    |                 |    BACKEND    |                 |   DATABASE    |
|   DEVELOPER   |                 |   DEVELOPER   |                 | ADMINISTRATOR |
+---------------+                 +---------------+                 +---------------+
| - User UI/UX  |                 | - Server APIs |                 | - Logic & Auth|                 | - DB Schemas  |
| - HTML/CSS/JS |                 | - Integrations|                 | - Optimization|
| - Responsiveness                |               |                 | - Backups/Sec |
+---------------+                 +---------------+                 +---------------+
```

### 1. Frontend Developer:
- **Primary Goal**: Build everything users interact with visually in the web browser.
- **Responsibilities**:
  - Converting UI/UX mockups into interactive HTML/CSS code.
  - Ensuring responsive design across mobile, tablet, and desktop screens.
  - Integrating APIs to send and display dynamic data seamlessly.

### 2. Backend Developer:
- **Primary Goal**: Build and maintain the server-side logic, application architecture, and data pipelines.
- **Responsibilities**:
  - Writing clean RESTful or GraphQL API endpoints.
  - Implementing security protocols, session management, and user authentication (OAuth, JWT).
  - Writing code that communicates with databases and external microservices.

### 3. Database Administrator (DBA):
- **Primary Goal**: Manage data integrity, security, availability, and database performance.
- **Responsibilities**:
  - Designing optimized database schemas, tables, and indexes.
  - Performing routine database backups, recovery procedures, and security auditing.
  - Tuning slow-running SQL queries to optimize throughput and handle heavy traffic loads.

---

## Question 7: Installing and Configuring VS Code for Web Development

### Step-by-Step Installation & Configuration Guide:

1. **Download & Install VS Code**:
   - Go to [code.visualstudio.com](https://code.visualstudio.com/) and download the installer for Windows/macOS.
   - Run the executable file and check **"Add to PATH"** and **"Open with Code"** context menu options.

2. **Essential Web Development Extensions to Install**:
   - **Live Server** (by Ritwick Dey): Launches a local development server with live reload feature for static pages.
   - **Prettier - Code Formatter**: Automatically formats HTML, CSS, and JavaScript code on save.
   - **Auto Rename Tag & Auto Close Tag**: Speeds up writing clean HTML code.
   - **ES7+ React/Redux/React-Native snippets**: Handy shortcuts for writing JS code.

3. **Setting Up a Sample HTML/CSS/JS Workspace**:
   - Open VS Code -> Click **File > Open Folder** -> Select project directory.
   - Create three main files:
     - `index.html`
     - `style.css`
     - `script.js`
   - Right-click `index.html` and click **"Open with Live Server"**.

```
Workspace Directory Structure:
├── index.html
├── style.css
└── script.js
```

---

## Question 8: Difference between Static and Dynamic Websites

| Aspect | Static Website | Dynamic Website |
| :--- | :--- | :--- |
| **Content Generation** | Delivered directly to browser exactly as stored on server disk. | Generated dynamically on-the-fly via server-side scripts and database queries. |
| **Interactivity** | Display-only or basic client-side form triggers; same content for all users. | Highly interactive, personalized feeds, user accounts, and real-time updates. |
| **Database Dependency** | Does **not** require a database. | **Requires** a database (MySQL, PostgreSQL, MongoDB) to store and fetch data. |
| **Development Cost & Speed** | Quick to build, inexpensive to host. | Complex architecture, requires more maintenance and resources. |

### Real-World Examples:
- **Static Website Example**: A company's **portfolio landing page** or a **restaurant menu page** where text and image files remain unchanged unless a developer manually updates the HTML file.
- **Dynamic Website Example**: **YouTube** or **Netflix**. Each logged-in user sees personalized recommended videos, custom playlists, comments, and account details based on their stored user profile and server data.

---

## Question 9: Five Web Browsers and Rendering Engines Comparison

| Web Browser | Rendering Engine | JavaScript Engine | Developed By | Key Characteristics |
| :--- | :--- | :--- | :--- | :--- |
| **Google Chrome** | **Blink** | V8 | Google / Chromium Project | Fast rendering speed, extensive DevTools, multi-process memory management. |
| **Mozilla Firefox** | **Gecko** | SpiderMonkey | Mozilla Foundation | Independent open-source engine, privacy-centric, parallel Quantum compositor engine. |
| **Apple Safari** | **WebKit** | JavaScriptCore (Nitro) | Apple Inc. | Deep OS integration on iOS/macOS, highly optimized for power and memory efficiency. |
| **Microsoft Edge** | **Blink** | V8 | Microsoft | Built on open-source Chromium, tight integration with Windows ecosystem. |
| **Brave Browser** | **Blink** | V8 | Brave Software | Built on Chromium; focuses on native ad/tracker blocking and enhanced privacy features. |

### Differences Between Rendering Engines:
1. **Source Code & Governance**: WebKit was created by Apple (forked from KHTML); Google later forked WebKit to create **Blink**. **Gecko** is independently developed by Mozilla from scratch.
2. **Layout & Standards Execution**: Engines interpret CSS rules, flexbox/grid layout spec implementations, and web APIs slightly differently, requiring cross-browser compatibility testing.
3. **Graphics & Compositing**: Gecko uses **WebRender** (Rust-based GPU rendering engine), whereas Blink utilizes **Skia** graphics library for hardware-accelerated drawing.

---

## Question 10: Web Architecture Flow Diagram — Client, Server, Database & APIs

### Architecture Flow Diagram:

```
 +------------------+                +------------------+                +------------------+
 |  CLIENT LAYER    |                |   SERVER LAYER   |                |  DATABASE LAYER  |
 |                  |                |                  |                |                  |
 | - Web Browser    |  1. Request    | - Web Server     |  3. SQL/Query  | - PostgreSQL /   |
 | - Mobile App     | -------------> | - API Gateway    | -------------> |   MongoDB        |
 |                  | (HTTP/JSON API)| - Business Logic |                |                  |
 | - User interface | <------------- |                  | <------------- | - Relational /   |
 |   rendering      |  4. Response   | - REST/GraphQL   |  2. Data Result|   Document data  |
 +------------------+   (JSON Data)  +------------------+                +------------------+
```

### Layer Components Explained:
1. **Client**: The frontend application (Browser or Mobile App) that interacts directly with the user. It captures inputs and dispatches HTTP requests via APIs.
2. **API (Application Programming Interface)**: Acts as the communication bridge/contract between Client and Server (typically RESTful JSON or GraphQL endpoints).
3. **Server**: Executes business logic, authenticates requests, processes incoming payloads, and talks to data layers.
4. **Database**: Securely stores, retrieves, updates, and deletes persistent application data (user records, products, logs).
