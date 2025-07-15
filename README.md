# 📚 NoteNest API

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**A comprehensive RESTful API for managing tutorials and notes, built with modern web technologies**

[![GitHub stars](https://img.shields.io/github/stars/YUKII2K3/-NoteNest-API?style=social)](https://github.com/YUKII2K3/-NoteNest-API)
[![GitHub forks](https://img.shields.io/github/forks/YUKII2K3/-NoteNest-API?style=social)](https://github.com/YUKII2K3/-NoteNest-API)
[![GitHub issues](https://img.shields.io/github/issues/YUKII2K3/-NoteNest-API)](https://github.com/YUKII2K3/-NoteNest-API/issues)
[![GitHub license](https://img.shields.io/github/license/YUKII2K3/-NoteNest-API)](https://github.com/YUKII2K3/-NoteNest-API/blob/main/LICENSE)

</div>

---

## 🎯 Project Overview

**NoteNest API** is a robust, scalable backend solution designed specifically for students and educators to manage tutorials, notes, and educational content. Built with industry-standard technologies, this API provides a solid foundation for building educational applications and learning management systems.

### 🌟 Key Features

- **🔧 Full CRUD Operations** - Complete Create, Read, Update, Delete functionality for tutorials and notes
- **🚀 RESTful Architecture** - Clean, intuitive REST API endpoints following best practices
- **🗄️ MongoDB Integration** - Robust database operations with Mongoose ODM for data modeling
- **🌐 CORS Support** - Cross-origin resource sharing enabled for frontend integration
- **🏗️ Modular Design** - Well-organized, maintainable code structure
- **📊 Search & Filter** - Advanced querying capabilities with MongoDB aggregation
- **🔍 Published/Unpublished States** - Content management with publication status
- **⚡ High Performance** - Optimized database queries and efficient data handling

### 🎓 Perfect For Students

- **Learning Backend Development** - Understand REST APIs, database design, and server architecture
- **Portfolio Project** - Showcase your full-stack development skills
- **Real-world Experience** - Work with production-ready technologies
- **Scalable Foundation** - Easy to extend and customize for your needs

---

## 🛠️ Technology Stack

| Component | Technology | Version | Purpose |
|-----------|------------|---------|---------|
| **Runtime** | Node.js | Latest LTS | JavaScript runtime environment |
| **Framework** | Express.js | 4.18.2+ | Web application framework |
| **Database** | MongoDB | Latest | NoSQL document database |
| **ODM** | Mongoose | 6.11.1+ | MongoDB object modeling |
| **CORS** | cors | 2.8.5+ | Cross-origin resource sharing |

### 🏗️ Architecture Overview

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Client App    │    │   NoteNest API  │    │    MongoDB      │
│   (Frontend)    │◄──►│   (Backend)     │◄──►│   (Database)    │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                              │
                    ┌─────────────────┐
                    │   Express.js    │
                    │   Server        │
                    └─────────────────┘
```

---

## 📋 API Endpoints

### 🎯 Tutorial Management

| Method | Endpoint | Description | Request Body | Response |
|--------|----------|-------------|--------------|----------|
| `GET` | `/api/tutorials` | Get all tutorials | - | Array of tutorials |
| `GET` | `/api/tutorials/:id` | Get tutorial by ID | - | Single tutorial |
| `POST` | `/api/tutorials` | Create new tutorial | `{title, description, published}` | Created tutorial |
| `PUT` | `/api/tutorials/:id` | Update tutorial | `{title, description, published}` | Success message |
| `DELETE` | `/api/tutorials/:id` | Delete tutorial | - | Success message |
| `DELETE` | `/api/tutorials` | Delete all tutorials | - | Success message |
| `GET` | `/api/tutorials/published` | Get published tutorials | - | Array of published tutorials |
| `GET` | `/api/tutorials?title=[keyword]` | Search tutorials by title | - | Filtered tutorials |

### 📝 Request/Response Examples

#### Create a Tutorial
```bash
POST /api/tutorials
Content-Type: application/json

{
  "title": "Introduction to Node.js",
  "description": "Learn the basics of Node.js development",
  "published": true
}
```

#### Response
```json
{
  "id": "507f1f77bcf86cd799439011",
  "title": "Introduction to Node.js",
  "description": "Learn the basics of Node.js development",
  "published": true,
  "createdAt": "2024-01-15T10:30:00.000Z",
  "updatedAt": "2024-01-15T10:30:00.000Z"
}
```

---

## 🚀 Getting Started

### 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v14.0.0 or higher)
- **npm** (v6.0.0 or higher)
- **MongoDB** (v4.4.0 or higher)
- **Git** (for cloning the repository)

### 🔧 Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/YUKII2K3/-NoteNest-API.git
   cd -NoteNest-API
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Configure Database**
   - Ensure MongoDB is running on your system
   - The application will automatically connect to `mongodb://0.0.0.0:27017/notenest_db`

4. **Start the Server**
   ```bash
   npm start
   ```

5. **Verify Installation**
   - Open your browser and navigate to `http://localhost:8080`
   - You should see: `{"message": "Welcome to NoteNest API."}`

### 🧪 Testing the API

You can test the API endpoints using tools like:
- **Postman** - API development and testing
- **cURL** - Command-line HTTP client
- **Thunder Client** - VS Code extension for API testing

#### Example cURL Commands

```bash
# Get all tutorials
curl -X GET http://localhost:8080/api/tutorials

# Create a new tutorial
curl -X POST http://localhost:8080/api/tutorials \
  -H "Content-Type: application/json" \
  -d '{"title":"My First Tutorial","description":"This is a test tutorial","published":true}'

# Get tutorial by ID (replace with actual ID)
curl -X GET http://localhost:8080/api/tutorials/507f1f77bcf86cd799439011
```

---

## 📁 Project Structure

```
notenest-api/
├── 📁 app/
│   ├── 📁 config/
│   │   └── 📄 db.config.js          # Database configuration
│   ├── 📁 controllers/
│   │   └── 📄 tutorial.controller.js # Business logic for tutorials
│   ├── 📁 models/
│   │   ├── 📄 index.js              # Database connection setup
│   │   └── 📄 tutorial.model.js     # Tutorial data model
│   └── 📁 routes/
│       └── 📄 turorial.routes.js    # API route definitions
├── 📄 server.js                     # Main application entry point
├── 📄 package.json                  # Project dependencies and scripts
├── 📄 .gitignore                    # Git ignore rules
└── 📄 README.md                     # Project documentation
```

### 🔍 Code Organization

- **`server.js`** - Application entry point, middleware setup, and server configuration
- **`app/config/`** - Configuration files for database and other services
- **`app/controllers/`** - Business logic and request handling
- **`app/models/`** - Database models and schema definitions
- **`app/routes/`** - API route definitions and endpoint mapping

---

## 🎓 Learning Objectives

This project is designed to help you master:

### 🏗️ Backend Development
- **RESTful API Design** - Learn to create clean, intuitive APIs
- **Database Modeling** - Understand MongoDB schema design with Mongoose
- **Server Architecture** - Build scalable Node.js applications
- **Error Handling** - Implement robust error management

### 🛠️ Technical Skills
- **Node.js & Express.js** - Modern JavaScript backend development
- **MongoDB & Mongoose** - NoSQL database operations
- **API Development** - RESTful service creation
- **Code Organization** - Modular, maintainable code structure

### 🚀 Best Practices
- **MVC Pattern** - Model-View-Controller architecture
- **Middleware Usage** - Request processing and validation
- **Database Operations** - Efficient querying and data manipulation
- **Project Structure** - Professional code organization

---

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the root directory for environment-specific configuration:

```env
PORT=8080
MONGODB_URI=mongodb://0.0.0.0:27017/notenest_db
NODE_ENV=development
```

### Database Configuration

The application connects to MongoDB with the following default settings:
- **Host**: `0.0.0.0`
- **Port**: `27017`
- **Database**: `notenest_db`

You can modify these settings in `app/config/db.config.js`.

---

## 🧪 Testing

### Manual Testing

Test the API endpoints using the provided examples or your preferred API testing tool.

### Automated Testing

To add automated testing to this project:

1. Install testing dependencies:
   ```bash
   npm install --save-dev jest supertest
   ```

2. Add test scripts to `package.json`:
   ```json
   {
     "scripts": {
       "test": "jest",
       "test:watch": "jest --watch"
     }
   }
   ```

3. Create test files in a `tests/` directory

---

## 🚀 Deployment

### Local Development
```bash
npm start
```

### Production Deployment

1. **Environment Setup**
   ```bash
   export NODE_ENV=production
   export PORT=3000
   ```

2. **Process Management**
   ```bash
   # Using PM2
   npm install -g pm2
   pm2 start server.js --name "notenest-api"
   ```

3. **Docker Deployment**
   ```dockerfile
   FROM node:16-alpine
   WORKDIR /app
   COPY package*.json ./
   RUN npm install
   COPY . .
   EXPOSE 8080
   CMD ["npm", "start"]
   ```

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### 🐛 Reporting Issues
- Use the GitHub issue tracker
- Provide detailed bug reports with steps to reproduce
- Include your environment details (OS, Node.js version, etc.)

### 💡 Suggesting Features
- Open a feature request issue
- Describe the use case and expected behavior
- Consider the impact on existing functionality

### 🔧 Code Contributions
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### 📝 Code Style
- Follow existing code formatting
- Add comments for complex logic
- Write meaningful commit messages
- Include tests for new features

---

## 📚 Additional Resources

### 📖 Documentation
- [Node.js Documentation](https://nodejs.org/docs/)
- [Express.js Guide](https://expressjs.com/en/guide/routing.html)
- [MongoDB Manual](https://docs.mongodb.com/manual/)
- [Mongoose Documentation](https://mongoosejs.com/docs/)

### 🎥 Tutorials
- [Node.js Crash Course](https://www.youtube.com/watch?v=fBNz5xF-Kx4)
- [Express.js Tutorial](https://www.youtube.com/watch?v=L72fhGm1tfE)
- [MongoDB Tutorial](https://www.youtube.com/watch?v=pWbMrx5rVBE)

### 🛠️ Tools
- [Postman](https://www.postman.com/) - API testing
- [MongoDB Compass](https://www.mongodb.com/products/compass) - Database GUI
- [VS Code](https://code.visualstudio.com/) - Code editor

---

## 📄 License

This project is licensed under the **ISC License** - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Yuktheshwar** - [GitHub Profile](https://github.com/YUKII2K3)

### 📞 Contact
- **GitHub**: [@YUKII2K3](https://github.com/YUKII2K3)
- **Email**: yuktheshwarshali@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/yuktheshwar-mp

---

## 🙏 Acknowledgments

- **Express.js Team** - For the amazing web framework
- **MongoDB Team** - For the powerful NoSQL database
- **Mongoose Team** - For the elegant ODM library
- **Node.js Community** - For the vibrant ecosystem

---

<div align="center">

**⭐ Star this repository if you found it helpful!**

**🔄 Fork it to create your own version!**

**🐛 Report issues to help improve the project!**

</div>
