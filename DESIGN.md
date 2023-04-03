# Overview

The One API SDK uses the `requests` library for making HTTP requests and provides a simple interface for 
interacting with The One API.

## Package management
`poetry` is used for managing dependencies and publishing to pypi.

## Features
- Rate limiting: The SDK implements rate limiting using the `RateLimitedAPI` class, 
which takes care of tracking request timestamps and enforcing the rate limit. Sliding window
strategy is used for rate limit monitoring.
- Pagination: The `list_movies` and `list_movie_quotes` methods support pagination through the `page`
and `limit` parameters.
- Filtering: The SDK supports filtering through the filters parameter in the `list_movies `
and `list_movie_quotes` methods. This allows users to pass a dictionary containing filter keys and
values, using MongoDB syntax.
- Error handling: The SDK raises an appropriate error if the API returns an unsuccessful response.

## Structure
The SDK has two main components:

- `RateLimitedAPI`: A base class that handles rate limiting and provides a simple interface for 
making HTTP requests.
- `TheOneAPIClient`: The main class that inherits from RateLimitedAPI and provides methods for 
interacting with The One API. 

The `TheOneAPIClient` class has the following methods:

- `get_movie`: Get a movie by its ID.
- `list_movies`: List movies with optional pagination and filters.
- `list_movie_quotes`: List movie quotes with optional pagination and filters.
