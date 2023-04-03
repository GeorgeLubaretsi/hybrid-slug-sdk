# The One API SDK

This is an SDK for The One API, a RESTful API providing information about The Lord of the Rings trilogy.

## Installation

```bash
pip install hybrid-slug
```

## Usage

Get the access token - [The One API](https://the-one-api.dev/sign-up)

```python
from hybrid_slug import TheOneAPIClient

access_token = "your_access_token"
client = TheOneAPIClient(access_token)

# Get a movie by ID
movie = client.get_movie("<movie-id>")

# List movies with pagination and filters
movies = client.list_movies(page=0, limit=10, filters={
    "sort": "name:asc",
    'name!': 'Frodo',
})

# List movie quotes with pagination and filters
quotes = client.list_movie_quotes("<movie-id>", page=0, limit=10, filters={
    "sort": "character:asc"
})

```

## Testing

TODO

