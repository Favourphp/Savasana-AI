# Savasana-AI
# DETAILED EXPLANATION OF THE SYSTEM DESIGN ARCHITECTURE
# Chrome Extension:

Background Script: Handles tasks that run in the background, manages the extension's lifecycle, and interacts with the Chrome browser.
Content Script: Executes in the context of a web page when the extension is activated. Communicates with the page and sends data to the background script.
Popup: User interface that appears when the extension icon is clicked. Allows users to interact with the extension.

Web Application:

Frontend: User interface visible to clients. Built using HTML, CSS, and JavaScript. Communicates with the backend through APIs to retrieve and display data.
Backend: Server-side logic responsible for processing requests, handling business logic, and interacting with the database.
Database: MongoDB is used for storing data. It provides a flexible, NoSQL storage solution suitable for the unstructured nature of message data.

Cloud Services:

Machine Learning Models: Hosted on a cloud platform (AWS SageMaker). Trained on client conversational message history to generate messages automatically.
API Gateway: AWS API Gateway facilitates communication between the web application and cloud services. Manages API requests and responses securely.
Message Queue: AWS Simple Queue Service (SQS) could be used for handling asynchronous communication between components, ensuring scalable and reliable message processing.

Data Flow:

The Chrome Extension sends data to the Web Application, triggering API requests.
The Web Application processes these requests, performs business logic, and interacts with the database.
The Cloud Services, including Machine Learning Models, generate messages based on historical data and respond to API requests.
API Interactions:

The Chrome Extension communicates with the Web Application using RESTful APIs. This includes sending and receiving data related to customer accounts and messaging.
The Web Application communicates with Cloud Services through APIs. This involves sending requests to the API Gateway, which then routes them to the appropriate service (e.g., Machine Learning Models).

Technology Choices Justification:

Plasmo for Chrome Extension: Chosen for its compatibility with Chrome and simplicity, facilitating communication between different parts of the extension.
Typescript and Express for Backend: TypeScript allows you to define types for request and response objects, middleware, and route handlers, providing better code understanding and validation, and Express simplifies the creation of robust APIs.
MongoDB for Database: NoSQL database chosen for its flexibility in handling unstructured data, essential for storing conversational message history.
AWS for Cloud Services: Leveraged for its scalability, reliability, and a suite of services (API Gateway, SageMaker, SQS) suitable for building a distributed and scalable system.
