# ALX Project 0x14 – MoviesDatabase API Documentation

## API Overview  
The MoviesDatabase API provides a RESTful web service that offers extensive metadata for movies, TV-series and episodes — including titles, descriptions, cast/crew, ratings, images and more. The service enables developers to search for content, retrieve detailed entries and integrate movie/series information into apps or websites.

## Version  
The version of the API as provided on RapidAPI is **v1**. :contentReference[oaicite:1]{index=1}

## Available Endpoints  
Here are key endpoints (note: endpoint names and parameters may vary; refer to the official docs for full list).  
- `/search`: Search for movies/series/episodes by title or other criteria.  
- `/details`: Retrieve full details for a given movie, series or episode (metadata, cast, crew, etc).  
- `/popular`: Get a list of popular titles.  
- `/top_rated`: Retrieve highest-rated titles overall.  
- `/images`: Fetch image assets (posters, backdrops) for a given title.  
- `/genres`: List available genres and corresponding IDs.  
- `/credits`: Get cast and crew information for a movie or series.  

## Request and Response Format  
### Request  
- Method: `GET` (or possibly `POST` depending on endpoint, check docs).  
- URL example: `https://api.moviesdatabase.com/v1/search?query=Inception&api_key=YOUR_API_KEY`  
- Request headers typically include: `Authorization: Bearer <API_KEY>` or `x-apikey` depending on service.  
- Query parameters might include `query`, `year`, `type` (movie/series), `page`.

### Response  
A typical JSON response might look like:
```json
{
  "status": "success",
  "data": {
    "results": [
      {
        "id": "tt1375666",
        "title": "Inception",
        "year": 2010,
        "type": "movie",
        "poster": "https://…",
        "rating": 8.8,
        "genres": ["Action","Sci-Fi"],
        "overview": "A thief who steals corporate secrets …"
      }
      // more items …
    ],
    "page": 1,
    "total_pages": 10,
    "total_results": 100
  }
}
