# omdb
Movie Search Application
This project is a simple web-based application that allows users to search for movies using the OMDb API and displays relevant details for each movie.

Features
Search Bar with Debounce: The application includes a search bar that triggers the movie search based on user input. The debounce feature is implemented to delay the API call until the user has stopped typing for 1 second (1000ms).
Movie List Display: A list of movies that match the search query is shown, each with a title and poster. The list is dynamically updated as the user types.
Movie Details on Click: Clicking on any movie from the search results displays detailed information about the selected movie, including title, release date, genre, and IMDb rating.
OMDb API Integration: The app uses the OMDb API to fetch movie data and details.

![Demo](https://github.com/PoojaR-17/omdb/blob/main/SS.png)
How It Works
Debounce Function
The debounce function is used to optimize the search process by waiting for a specific period of inactivity before making the API request. This prevents unnecessary API calls on each keystroke.

javascript
Copy code
let timerId;
function debounce(func, wait) {
  if (timerId) {
    clearTimeout(timerId);
  }
  timerId = setTimeout(func, wait);
}
Search Functionality
When the user inputs text into the search bar, the app triggers the getMoviesList function after the debounce period. This function calls the OMDb API with the user's search query and fetches a list of movies.

javascript
Copy code
document.querySelector("#searchBar").addEventListener("input", () => {
  debounce(getMoviesList, 1000);
});
Display Movie List
The showMovieList function renders the list of movies that match the search query. Each movie entry is clickable, allowing the user to select and view more detailed information about the movie.

javascript
Copy code
function showMovieList(data) {
  data.forEach((element) => {
    // Create elements for movie poster and title
    // Attach click event to fetch detailed movie data
  });
}
Fetch and Display Movie Details
Upon clicking on a movie, the app fetches detailed information about the selected movie using the OMDb API and displays it in a card format.

javascript
Copy code
async function getMovieData(movieName) {
  // Fetch detailed movie data using the movie title
}

function displayCard(data) {
  // Render movie details like title, release date, genre, and IMDb rating
}
API Keys
You need an OMDb API key to fetch data. Replace the placeholder API_KEY variable with your actual OMDb API key.
javascript
Copy code
let API_KEY = 'your_api_key_here';
How to Run
Clone: https://github.com/PoojaR-17/omdb
or download this project.
Replace the API key in the script with your own OMDb API key.
Open the index.html file in your browser.
Start typing in the search bar to find movies and click on a movie to view its details.
Technologies Used
HTML: For structuring the web page.
CSS: For styling the elements.
JavaScript: For implementing the search functionality, API integration, and dynamic content rendering.
OMDb API: For fetching movie data.
