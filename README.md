# Aigeon AI Google Local Search

Aigeon AI Google Local Search is a Python-based server application designed to interface with the Google Local search engine through the SerpApi service. This application provides a robust tool for scraping and retrieving localized search results from Google, allowing users to simulate searches from specific locations and devices.

## Features Overview

- **Local Search Simulation**: Simulate Google Local searches from specified locations and devices.
- **Customizable Search Parameters**: Configure search queries with various parameters such as location, language, and device type.
- **Pagination Support**: Manage search results with pagination by specifying the result offset.
- **Cache Management**: Control caching behavior to optimize search performance and cost.
- **Asynchronous Search Submission**: Submit searches asynchronously for later retrieval, enhancing efficiency in handling large volumes of search requests.

## Main Features and Functionality

### Local Search Tool

The core functionality of this application is encapsulated in the `search_local` tool, which allows users to perform Google Local searches with a high degree of customization. This tool leverages the SerpApi service to fetch search results based on user-defined parameters.

- **Query Parameter (`q`)**: Define the search query, similar to a regular Google Local search.
- **Location Parameter (`location`)**: Specify the origin of the search to simulate a real user's search from a particular city or region.
- **Encoded Location (`uule`)**: Use Google encoded location for precise search origin control.
- **Google Domain (`google_domain`)**: Choose the Google domain for the search, defaulting to `google.com`.
- **Country Code (`gl`)**: Set the country for the search using a two-letter country code.
- **Language Code (`hl`)**: Define the language for the search using a two-letter language code.
- **Pagination (`start`)**: Control the result offset for pagination, supporting both desktop and mobile result sets.
- **Device Type (`device`)**: Select the device type for the search results, such as desktop, tablet, or mobile.
- **Cache Control (`no_cache`)**: Decide whether to use cached results or force a fresh search.
- **Asynchronous Submission (`async`)**: Opt for asynchronous search submission to retrieve results later.

### Main Functions Description

- **`search_local`**: This function is the primary tool for executing Google Local searches. It constructs a payload with the specified parameters and sends a GET request to the SerpApi service. The function returns the search results in JSON format. The payload is dynamically constructed to include only non-null parameters, ensuring efficient API requests.

- **Server Initialization**: The server is initialized using the `FastMCP` framework, which handles incoming requests and executes the `search_local` tool based on user input. The server listens for connections and processes search requests, providing a streamlined interface for interacting with the Google Local search engine.

This application is a powerful tool for developers and businesses looking to integrate Google Local search capabilities into their workflows, providing flexibility and control over search parameters to tailor results to specific needs.