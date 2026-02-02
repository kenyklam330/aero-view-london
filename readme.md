# AeroView: London

A simple flight simulator experience that lets you pilot an A380 over the skies of London. Built with the Google Maps JavaScript API and its WebGL-powered 3D capabilities.

*(Suggestion: Replace the placeholder below with a screenshot or GIF of the game in action.)*


## Live Demo

A live version of this project can be found here: [**Fly Now!**](https://kenyklam330.github.io/aero-view-london/)

## Features

*   **Immersive 3D Flight:** Explore a 3D vector map of London from the cockpit.
*   **Dynamic UI:** A retro-style heads-up display (HUD) shows your speed and remaining fuel.
*   **Simple Controls:** Easy-to-learn controls for speed and steering.
*   **Dual Map Modes:** Switch between a stylized 3D Vector map and realistic Google Earth satellite imagery.
*   **Mini-Map:** Keep your bearings with a top-down mini-map.
*   **Dynamic Setup:** Automatically uses API keys if provided via CI/CD, otherwise prompts for manual entry.

## Setup and Configuration

To run this project locally, you need a Google Maps API Key and a Map ID with 3D vector mapping enabled.

### 1. Get a Google Maps API Key

1.  Go to the [Google Cloud Console](https://console.cloud.google.com/).
2.  Create a new project or select an existing one.
3.  Navigate to **APIs & Services > Credentials**.
4.  Click **Create Credentials > API key**.
5.  **Important:** Restrict your API key! For local development, you can restrict it by HTTP referrers (e.g., `localhost:*`). For production, restrict it to your domain.
6.  Make sure the **Maps JavaScript API** is enabled for your project.

### 2. Get a Map ID

1.  In the Google Cloud Console, navigate to **Google Maps Platform > Map Management**.
2.  Click **Create New Map ID**.
3.  Give it a name, select **JavaScript** as the platform, and choose the **Vector** map type.
4.  Under "Map features", enable **Tilt** and **Rotation**.
5.  Save the Map ID.

### 3. Running the Game

There are two ways to provide your credentials to the game:

**Option A: Manual Entry (Easiest for local testing)**

1.  Simply open `index.html` in your browser.
2.  The game will prompt you to enter your API Key and Map ID.
3.  Enter the credentials you obtained in the steps above. The game will save them to your browser's `localStorage` for future sessions.

**Option B: CI/CD (For deployment)**

The project is set up to have placeholders `__API_KEY__` and `__MAP_ID__` in `index.html`. A GitHub Action or other CI/CD pipeline can use `sed` or a similar tool to replace these placeholders with your actual credentials (stored as secrets) during the build process.

```javascript
// Placeholder for GitHub Secrets injection
// DO NOT MANUALLY CHANGE THE LINE BELOW
const CONFIG_FROM_GITHUB = { API_KEY: "__API_KEY__", MAP_ID: "__MAP_ID__" };
```

## How to Play

*   **W:** Increase speed
*   **S:** Decrease speed
*   **A:** Steer left (yaw)
*   **D:** Steer right (yaw)

Watch your fuel! The game ends when you run out.

## Technology Stack

*   **HTML5 / CSS3 / Vanilla JavaScript**
*   **Google Maps JavaScript API** (with WebGL-powered Vector Maps)

## Author

*   **Ken Lam**
    *   LinkedIn: [ken-yiu-kei-lam](https://www.linkedin.com/in/ken-yiu-kei-lam/)
    *
    *   Email: `kenyklam330@gmail.com`