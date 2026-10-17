# Atmos-Data — Weather App

A React-based weather application that retrieves current weather information for a city using the OpenWeatherMap API. Built with React, Vite, Axios, and Bootstrap, the project demonstrates API integration, state management, asynchronous HTTP requests, and dynamic UI rendering.

## Overview

Atmos-Data allows users to search for a city and view its current temperature in Celsius. The application fetches weather data from OpenWeatherMap and renders the results using React.

The project is also a practical learning exercise in modern React development and Vite-based tooling.

## Features

- **City-based weather search:** Enter a city name and retrieve its current weather data.
- **API integration:** Fetch weather information from OpenWeatherMap.
- **Temperature conversion:** Convert the API's Kelvin temperature to Celsius.
- **Dynamic rendering:** Display weather information using React state.
- **Responsive styling foundations:** Use Bootstrap 5 and custom CSS.
- **Modern development tooling:** Use Vite for the development server and production builds.

## Tech Stack

| Technology | Purpose |
|---|---|
| React | Build the user interface |
| JavaScript (ES6+) | Application logic |
| Vite | Development server and build tool |
| Axios | Make HTTP requests |
| Bootstrap 5 | UI styling and layout |
| CSS | Custom styling |
| OpenWeatherMap API | Retrieve current weather data |
| npm | Manage dependencies and project scripts |

## Getting Started

### Prerequisites

Install the following:

- Node.js and npm
- Git
- An OpenWeatherMap API key
- An internet connection

Verify your Node.js and npm installations:

```bash
node -v
npm -v
```

Use a Node.js version supported by your installed Vite release.

### Installation

Clone the repository:

```bash
git clone https://github.com/VajraX14/Atmos-Data.git
```

Navigate to the project directory:

```bash
cd Atmos-Data
```

Install the project dependencies:

```bash
npm install
```

### API Configuration

Atmos-Data uses the OpenWeatherMap API to retrieve current weather information.

1. Create an account at [OpenWeatherMap](https://openweathermap.org/api).
2. Obtain an API key.
3. Create a file named `.env.local` in the project root, in the same directory as `package.json`.
4. Add your API key:

```text
VITE_OPENWEATHER_API_KEY=your_api_key_here
```

In `src/App.jsx`, read the variable using:

```javascript
const apiKey = import.meta.env.VITE_OPENWEATHER_API_KEY;
```

**Important security note:** Variables prefixed with `VITE_` are exposed to client-side code. A `.env.local` file helps keep local configuration out of source control, but it does not make the API key secret in a deployed browser application. For stronger protection, make API requests through a backend or serverless function. Never commit your actual API key to a public repository.

### Run the Application

Start the Vite development server:

```bash
npm run dev
```

Open the local URL printed in your terminal. By default, Vite uses:

```text
http://localhost:5173
```

You can also use the following command if the `start` script is configured in `package.json`:

```bash
npm start
```

## Available Scripts

| Command | Description |
|---|---|
| `npm run dev` | Start the Vite development server |
| `npm start` | Start the development server, if configured as `vite` |
| `npm run build` | Create an optimized production build |
| `npm run preview` | Preview the production build locally |

The production build is written to the `dist/` directory by default.

### Build for Production

Create a production build:

```bash
npm run build
```

Preview the generated build locally:

```bash
npm run preview
```

Test the application using the preview URL printed in your terminal before deploying it.

## How It Works

1. The user enters a city name in the search field.
2. React stores the input using the `useState` hook.
3. Clicking **Search** triggers the weather-fetching function.
4. Axios sends an HTTP request to the OpenWeatherMap current-weather endpoint.
5. The application receives the response and stores the weather data in React state.
6. React updates the interface with the returned city name and temperature.
7. The temperature is converted from Kelvin to Celsius before display.

## Project Structure

The following is the intended structure for the Vite version after completing the migration:

```text
Atmos-Data/
├── public/
│   ├── favicon.ico
│   ├── logo192.png
│   ├── logo512.png
│   └── manifest.json
├── src/
│   ├── App.jsx
│   ├── App.css
│   ├── main.jsx
│   ├── index.css
│   ├── reportWebVitals.js    # Optional
│   └── setupTests.js         # Optional; requires test-runner configuration
├── .env.local                # Local API configuration; do not commit
├── .gitignore
├── index.html                # Vite HTML entry point
├── package.json
├── package-lock.json
├── vite.config.js
└── README.md
```

Some optional files may be absent depending on which features you retain.

## Migration from Create React App to Vite

This project uses Vite instead of Create React App (CRA) for development and production builds.

The migration involves:

- Replacing `react-scripts` with Vite and `@vitejs/plugin-react`.
- Replacing CRA scripts with Vite scripts.
- Moving `index.html` from `public/` to the project root.
- Using a Vite module script to load `src/main.jsx`.
- Renaming the React entry file from `src/index.js` to `src/main.jsx`.
- Using `import.meta.env` for Vite environment variables.
- Updating the README and `.gitignore` for Vite's commands and `dist/` output directory.

React components, hooks, Axios requests, Bootstrap styles, and ordinary CSS can generally be retained. However, CRA-specific configuration, environment variables, and test-runner assumptions need to be migrated separately where applicable.

## Current Limitations

- The application displays the city name and temperature rather than a full weather report.
- API errors are logged to the browser console instead of being displayed as user-friendly messages.
- A loading indicator is not currently implemented.
- Automated tests for API requests and error handling have not been configured.
- A browser-based API key cannot be kept secret solely by storing it in an environment variable.

## Potential Improvements

- Display weather conditions, humidity, wind speed, and weather icons.
- Add loading states and user-friendly error messages.
- Allow users to search by pressing Enter.
- Improve mobile layouts and accessibility.
- Add automated tests using Vitest and React Testing Library.
- Introduce a backend or serverless function for API requests.
- Add weather forecasts and historical weather visualizations.
- Configure continuous integration to run checks and production builds automatically.
- Deploy the application to a static hosting provider.

## Learning Objectives

This project provides practical experience with:

- React components and JSX.
- State management with `useState`.
- Handling user input and events.
- Making asynchronous API requests with Axios.
- Rendering data conditionally.
- Styling interfaces with Bootstrap and CSS.
- Managing dependencies with npm.
- Using Vite for local development and production builds.
- Configuring environment variables.
- Preparing a React application for deployment.

## Troubleshooting

### The development server does not start

Confirm that you are in the project root and that dependencies are installed:

```bash
npm install
npm run dev
```

Check the terminal output for missing dependencies, Node.js compatibility issues, or configuration errors.

### Weather data does not appear

Check that:

- Your API key is configured correctly in `.env.local`.
- The environment variable name begins with `VITE_`.
- You restarted the Vite development server after changing environment variables.
- The city name is valid.
- Your API key is active and your API access is available.
- The browser console and terminal do not show request errors.

### The production build fails

Run:

```bash
npm run build
```

Read the first error in the terminal output and resolve missing imports, syntax errors, or configuration problems before attempting deployment again.

## License

No license has currently been specified. Contact the repository owner before redistributing or reusing this project.

---

**Repository:** [VajraX14/Atmos-Data](https://github.com/VajraX14/Atmos-Data)

**Built with React and Vite.**
