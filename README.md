# Mobiliar - AI Assistant with Face Recognition

A web-based digital twin interface that combines real-time face recognition with an interactive D-ID AI Agent. This application runs entirely in the browser, detecting faces via the webcam and identifying specific users while hosting a conversational AI avatar.

## Features

* **Dual-Panel Interface:** Split-screen layout featuring a D-ID AI Agent (top) and live computer vision feed (bottom).
* **Real-time Face Detection:** Utilizes `face-api.js` (TinyFaceDetector) for high-performance face tracking directly in the browser.
* **User Recognition:** Identifies known users based on reference images and Euclidean distance matching.
* **Live Statistics:** Displays real-time FPS (Frames Per Second), total faces detected, and known users identified.
* **Responsive Design:** Adapts layout for mobile devices and laptops.
* **Privacy Focused:** All face detection processing happens locally on the client side; video streams are not sent to a server for detection.

## Tech Stack

* **HTML5 / CSS3:** Responsive Grid & Flexbox layout.
* **JavaScript (ES6+):** Async/await implementation for model loading and media handling.
* **[face-api.js](https://github.com/justadudewhohacks/face-api.js/):** JavaScript API for face detection and face recognition.
* **[D-ID Agent API](https://www.d-id.com/):** Embeddable conversational AI avatar.

## Prerequisites

To run this project, you need:
1.  A modern web browser (Chrome, Edge, Firefox, Safari).
2.  A webcam.
3.  **Important:** Due to browser security restrictions regarding camera access, **this file must be served via HTTP/HTTPS**. You cannot simply double-click the HTML file (`file://` protocol will block the camera).

## Quick Start

1.  **Clone or Download** this repository.
2.  **Start a local server** in the project directory.
    * *If you have Python installed:*
        ```bash
        python -m http.server 8000
        ```
    * *If you use VS Code:*
        Install the "Live Server" extension, right-click the HTML file, and select "Open with Live Server".
    * *Via Node.js:*
        ```bash
        npx serve
        ```
3.  Open your browser and navigate to `http://localhost:8000` (or the port specified).
4.  Allow camera permissions when prompted.

## Configuration

### Adding/Changing Known Faces
To customize who the application recognizes, modify the `REFERENCE_PEOPLE` array in the `<script>` section of the HTML file:

```javascript
const REFERENCE_PEOPLE = [
    { 
        name: 'YourName', 
        imageUrl: 'path/to/your/image.jpg' // Can be a local path or URL
    },
    // Add more people here
];
