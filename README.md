# Atmos-Data — Weather App

A React-based weather application that retrieves current weather data for a city using the OpenWeatherMap API. The project demonstrates API integration, React state management, asynchronous HTTP requests, and component-based UI development.

## Overview

Atmos-Data lets users enter a city name and retrieve its current temperature. Weather information is displayed through a simple interface built with React and Bootstrap.

## Features

- **City-based search:** Enter a city name to request its weather data.
- **Live API integration:** Fetch current weather information from OpenWeatherMap.
- **Temperature conversion:** Convert temperatures from Kelvin to Celsius.
- **Dynamic rendering:** Display the city name and temperature using React state.
- **Responsive UI foundations:** Use Bootstrap's layout and styling utilities.

## Tech Stack

| Technology | Purpose |
|---|---|
| React | Build the user interface |
| JavaScript | Application logic |
| Axios | Make HTTP requests |
| Bootstrap 5 | UI styling and layout |
| CSS | Custom visual styling |
| OpenWeatherMap API | Retrieve weather data |
| Create React App | Development and build tooling |

## Getting Started

### Prerequisites

- Node.js and npm
- An internet connection
- An OpenWeatherMap API key

### Installation

Clone the repository:

```bash
git clone https://github.com/VajraX14/Atmos-Data.git
cd Atmos-Data
```

Install the dependencies:

```bash
npm install
```

### API Configuration

Obtain an API key from [OpenWeatherMap](https://openweathermap.org/api).

The current implementation reads the API key from `src/App.js`, in the `apiKey` constant. Configure your own key there for local development.

**Security note:** Do not commit API keys to a public repository. For a publicly deployed application, use a backend to protect the key and restrict its usage.

### Run the Application

Start the development server:

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## How It Works

1. The user enters a city name.
2. React stores the input using `useState`.
3. Clicking **Search** triggers an Axios request to the OpenWeatherMap current-weather endpoint.
4. The application receives the API response and stores the weather data in React state.
5. React renders the returned city name and temperature, converted from Kelvin to Celsius.

## Project Structure

```text
Atmos-Data/
├── public/
│   └── index.html
├── src/
│   ├── App.js             # Weather search and API logic
│   ├── App.css            # Weather interface styling
│   ├── index.js           # Application entry point
│   ├── index.css          # Global styling
│   ├── reportWebVitals.js # Performance measurement helper
│   └── setupTests.js      # Test configuration
├── package.json           # Dependencies and scripts
├── package-lock.json      # Locked npm dependency tree
└── README.md
```

## Available Scripts

| Command | Purpose |
|---|---|
| `npm start` | Start the development server |
| `npm test` | Run the test suite |
| `npm run build` | Create a production build |
| `npm run eject` | Expose Create React App configuration (one-way operation) |

## Current Limitations

- Weather information is displayed only after a successful search.
- API errors are logged to the console rather than displayed in the interface.
- The current interface displays the city name and temperature, not a full forecast.
- The project does not yet include automated tests for weather fetching or error handling.

## Potential Improvements

- Add loading indicators and user-friendly error messages.
- Display weather conditions, humidity, wind speed, and weather icons.
- Support searches using the Enter key.
- Improve mobile layouts and accessibility.
- Add automated tests for API requests and UI behavior.
- Move API requests behind a backend before public deployment.

## Learning Objectives

This project provides practical experience with React hooks, controlled inputs, asynchronous API requests, HTTP response handling, conditional rendering, and CSS-based UI development.

## License

No license has currently been specified. Contact the repository owner before redistributing or reusing the project.

---

**Repository:** [VajraX14/Atmos-Data](https://github.com/VajraX14/Atmos-Data)
