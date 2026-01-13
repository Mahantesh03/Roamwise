# 🗺️ Roamwise - Smart Travel Planner

An intelligent travel planning application powered by AI that helps users create personalized itineraries for their trips.

## ✨ Features

- **🤖 AI-Powered Itinerary Generation** - Instantly generate custom travel itineraries based on your preferences
- **💾 Save & Manage Itineraries** - Authenticated users can save and revisit their travel plans
- **🔐 Role-Based Access Control** - Secure system with MEMBER and ADMIN roles
- **🌐 RESTful API** - Clean and scalable REST endpoints built with Spring Boot
- **📧 Email Services** - User registration and notification system
- **🌤️ Weather Integration** - Real-time weather information for destinations
- **📍 Place Search** - Discover interesting places and attractions for your trip

## 🛠️ Tech Stack

**Backend:**
- Spring Boot
- Java
- Maven
- Spring Security
- RESTful APIs

**Frontend:**
- HTML5
- CSS3
- JavaScript

**APIs & Services:**
- Weather API
- Places API
- Email Service

## 📁 Project Structure
```
Roamwise/
├── src/
│   ├── main/
│   │   ├── java/com/jsp/roam_smart/
│   │   │   ├── controller/
│   │   │   ├── service/
│   │   │   ├── repository/
│   │   │   ├── model/
│   │   │   └── exception/
│   │   └── resources/
│   └── test/
├── frontend/
└── pom.xml
```

## 🚀 Getting Started

### Prerequisites
- Java 17 or higher
- Maven 3.6+
- MySQL (or your preferred database)

### Installation

1. **Clone the repository**
```bash
   git clone https://github.com/Mahantesh03/Roamwise.git
   cd Roamwise
```

2. **Configure database** (update `application.properties`)
```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/roamwise
   spring.datasource.username=your_username
   spring.datasource.password=your_password
```

3. **Build the project**
```bash
   mvn clean install
```

4. **Run the application**
```bash
   mvn spring-boot:run
```

5. **Access the application**
   - Open your browser and go to `http://localhost:8080`

## 📝 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register new user |
| POST | `/api/auth/login` | User login |
| GET | `/api/itinerary` | Get user itineraries |
| POST | `/api/itinerary/generate` | Generate new itinerary |
| GET | `/api/places/search` | Search places |
| GET | `/api/weather` | Get weather info |

## 👥 Contributors

- **Mahantesh03** - Developer
- Original project inspiration: [roam-smart](https://github.com/1sanji1/roam-smart) by 1sanji1

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Contact

Mahantesh03 - [@Mahantesh03](https://github.com/Mahantesh03)

Project Link: [https://github.com/Mahantesh03/Roamwise](https://github.com/Mahantesh03/Roamwise)

---

⭐ If you find this project useful, please consider giving it a star!
