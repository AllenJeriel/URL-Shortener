
# URL Shortener: Create Your Own Link Shortening Service

URL Shorteners are a convenient solution to convert long and unwieldy URLs into short, memorable links that are easy to share. This mini-project is a full-fledged backend implementation of a URL Shortener built using the following technologies:

- FastAPI (Python)
- Redis Cache
- MongoDB

## Key Features

- Shorten lengthy URLs into compact and user-friendly links.
- Directly visit the original webpage by simply pasting the short URL into your browser.
- Efficiently delete short URLs as needed.
- Create custom short URLs that are easy to remember and share.


## Installation

1. **Docker Setup**

   Start by installing Docker on your system. Docker is essential for containerizing the necessary components.

2. **Redis Cache Configuration**

   Launch a Redis container with the following command to run a Redis server:

   ```sh
   docker run -d --name redis-container -p 6379:6379 redis:latest
   ```

3. **MongoDB Setup**

   Set up a MongoDB container and enable authentication by executing this command:

   ```sh
   docker run -d --name mongodb-container -p 27017:27017 \       
     -e MONGO_INITDB_ROOT_USERNAME=admin \
     -e MONGO_INITDB_ROOT_PASSWORD=admin \
     mongo:latest
   ```

4. **Virtual Environment Creation**

   Create a Python virtual environment to keep your project dependencies isolated. 

5. **Prerequisite Installation**

   Install the required Python packages by running the following command:

   ```sh
   pip install -r requirements.txt
   ```

6. **Running the Application**

   Start the FastAPI application using this command:

   ```sh
   uvicorn api:app --reload
   ```

## Running the Application

1. **Shortening a URL**

   You can shorten a URL by sending a POST request with a JSON payload containing the long URL. Replace `https://www.ex.com` with the URL you want to shorten:

   ```sh
   curl -X POST -H "Content-Type: application/json" -d '{"url": "https://www.ex.com"}' http://localhost:8000/shorten
   ```

2. **Using the Short URL**

   - Open a web browser.
   - Paste the short URL generated in the previous step.
   - You'll be seamlessly redirected to the original long URL.

3. **Deleting a Short URL**

   To remove a short URL, use the following command. Replace `http://localhost:8000/yCypqR+` with the actual short URL you want to delete:

   ```sh
   curl -X DELETE http://localhost:8000/yCypqR+ -i
   ```

   







