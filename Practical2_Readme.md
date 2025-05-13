# Practical 2: RESTful API Weather Application

## Project Overview
A weather application that interacts with two public APIs:
- **OpenWeatherMap API** (GET requests for weather data)
- **JSONPlaceholder API** (POST/PUT/DELETE requests for saved locations)

## Features
- Get current weather by city name
- Save favorite locations
- Edit and delete saved locations
- Tabbed interface for different operations

## Setup Instructions

### Prerequisites
- OpenWeatherMap API key (free tier)
- Modern web browser

### Installation
1. Clone the repository:
   ```bash
   git clone [your-repo-url]
   cd weather-api-app
   ```
2. Get your API key:
- Sign up at OpenWeatherMap
- Get your free API key

3. Configure the application:
- Open script.js
- Replace YOUR_OPENWEATHERMAP_API_KEY with your actual key

4. Run the application:
- Open index.html in any modern browser
- No server required

## Project Structure
```
weather-api-app/
├── index.html       # Main UI with forms and display
├── script.js        # All JavaScript functionality
└── README.md
```

## API Endpoints Used
1. OpenWeatherMap (GET)
```
https://api.openweathermap.org/data/2.5/weather?q={city}&appid={API_KEY}
```

2. JSONPlaceholder (CRUD operations)
```
POST/PUT/DELETE https://jsonplaceholder.typicode.com/posts
```

## Usage Guide
1. Weather Lookup (GET)
- Enter a city name
- Click "Get Weather"
- View results in the display area

2. Save Location (POST)
- Fill out the location form
- Click "Save Location"
- View in saved locations list

3. Edit Location (PUT)
- Click "Edit" on any saved location
- Modify the data in the popup
- Click "Update"

4. Delete Location (DELETE)
- Click "Delete" on any saved location
- Confirm deletion