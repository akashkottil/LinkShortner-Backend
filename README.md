# LinkShortner-Backend

This is a simple URL shortener backend built with Node.js, Express, and MongoDB. It allows users to generate short URLs, retrieve original URLs, and delete shortened URLs.

## 🚀 Features
- **Create Short URLs**: Convert long URLs into short, easy-to-share links.
- **Redirect to Original URL**: Users are redirected when they visit a short URL.
- **Delete Short URLs**: Remove shortened URLs when they are no longer needed.
- **Express API**: RESTful API built with Express.js.
- **MongoDB Database**: Stores URL mappings.
- **Environment Variables Support**: Uses .env for configuration.
- **Utility Functions**: Includes helper functions for unique ID generation and URL validation.

## 🛠 Tech Stack
- **Node.js** - JavaScript runtime
- **Express.js** - Web framework for Node.js
- **MongoDB** - NoSQL database for storing URL mappings
- **Mongoose** - ODM for MongoDB
- **nanoid** - Generates unique short URL IDs
- **dotenv** - Loads environment variables
- **cors** - Enables Cross-Origin Resource Sharing (CORS)
- **nodemon** - Auto-restarts server during development

## 📦 Installation

### 1️⃣ Clone the repository
```sh
git clone https://github.com/akashkottil/LinkShortner-Backend.git
cd LinkShortner-Backend
```

### 2️⃣ Install dependencies
```sh
npm install
```

### 3️⃣ Setup environment variables
Create a `.env` file in the root directory:
```
MONGO_URI=your_mongodb_connection_string
PORT=5000
BASE_URL=http://localhost:5000
```

### 4️⃣ Start the server

#### Development mode (with auto-restart)
```sh
npm run dev
```

#### Production mode
```sh
npm start
```
The server will start on `http://localhost:5000` (or the port specified in the .env file).

## 📌 API Endpoints

### ➤ Create a Short URL
- **Endpoint**: `POST /`
- **Body**:
```json
{
  "originalUrl": "https://example.com"
}
```
- **Response**:
```json
{
  "shortUrl": "http://localhost:5000/abc123"
}
```

### ➤ Redirect to Original URL
- **Endpoint**: `GET /:shortUrlId`
- **Example**: `GET /abc123`
- **Response**: Redirects to the original URL.

### ➤ Delete a Short URL
- **Endpoint**: `DELETE /`
- **Body**:
```json
{
  "shortUrlId": "abc123"
}
```
- **Response**:
```json
{
  "message": "Short URL deleted successfully"
}
```

## 🏗 Project Structure
```
📂 LinkShortner-Backend
 ┣ 📂 controllers
 ┃ ┗ 📜 url.js        # URL handling logic
 ┣ 📂 models
 ┃ ┗ 📜 Url.js        # Mongoose schema for storing URLs
 ┣ 📂 routes
 ┃ ┗ 📜 url.js        # API routes
 ┣ 📂 utils
 ┃ ┣ 📜 generateUniqueId.js   # Function to generate unique short URL IDs
 ┃ ┗ 📜 validateUrl.js        # Function to validate URLs
 ┣ 📜 server.js       # Main server entry point
 ┣ 📜 .env            # Environment variables
 ┣ 📜 .gitignore      # Files to ignore in Git
 ┣ 📜 package.json    # Project dependencies
 ┣ 📜 README.md       # Documentation
```

## 📌 License
This project is licensed under the MIT License.

## 💡 Contributing
Feel free to fork this repository and submit pull requests! 🚀

## 📞 Contact
- **GitHub**: [akashkottil](https://github.com/akashkottil)
- **Email**: [thedeveloperkot@gmail.com](mailto:thedeveloperkot@gmail.com)

Happy coding! 🎉🚀
