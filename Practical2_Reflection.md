# Practical 2 Reflection: RESTful API Weather App

## Documentation

### Implemented Features
1. **API Integration**
   - Successfully connected to two public APIs:
     - OpenWeatherMap for real-time weather data
     - JSONPlaceholder for mock CRUD operations

2. **CRUD Operations**
   - GET: Fetch weather data by city name
   - POST: Save new locations
   - PUT: Update existing locations
   - DELETE: Remove saved locations

3. **User Interface**
   - Tab system for different operations
   - Forms with validation
   - Modal for editing locations
   - Responsive results display

### Technical Approach
- Used vanilla JavaScript (no frameworks)
- Implemented Fetch API for all HTTP requests
- Structured code with separate functions for each operation
- Error handling for API failures

## Reflection

### Key Learnings
1. **API Integration**
   - Learned to work with different API response formats
   - Understood API key security best practices
   - Mastered parsing JSON responses

2. **Asynchronous JavaScript**
   - Gained experience with async/await
   - Learned proper error handling in Fetch
   - Implemented loading states

3. **CRUD Operations**
   - Understood HTTP methods deeply
   - Learned to structure payloads for POST/PUT
   - Implemented proper request headers

### Challenges Faced

#### Challenge 1: CORS Issues
**Issue:** Blocked by CORS policy when testing locally  
**Solution:**
- Used JSONPlaceholder instead of a mock local server
- Learned about CORS and its security implications
- Implemented proper error messages for users

#### Challenge 2: API Response Handling
**Issue:** Inconsistent weather API responses  
**Solution:**
- Added comprehensive error checking
- Implemented default values for missing data
- Added user feedback for invalid cities

```javascript
// Example error handling
try {
  const response = await fetch(weatherUrl);
  if (!response.ok) throw new Error('City not found');
  // ... process data
} catch (error) {
  showError(error.message);
}
```

#### Challenge 3: State Management
**Issue:** Tracking saved locations between operations
**Solution:**
- Implemented simple array-based state
- Added UI synchronization after each operation
- Used temporary IDs for mock API operations

### Future Improvements
1. Enhanced Features
- Add weather forecasts (5-day/3-hour)
- Implement local storage for persistence
- Add location search with autocomplete

2. UI/UX Improvements
- Better loading indicators
- Animated transitions
- Responsive design for mobile

3. Technical Upgrades
- Convert to TypeScript
- Add proper unit tests
- Implement a real backend service

### Conclusion
This project provided valuable experience in working with RESTful APIs and implementing full CRUD functionality. The hands-on practice with asynchronous JavaScript and error handling has significantly improved my web development skills.