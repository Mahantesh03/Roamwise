# 🗺️ Roamwise - Smart Travel Planner

An intelligent travel planning application powered by AI that helps users create personalized itineraries for their trips using Spring Boot and external APIs.

## ✨ Features

- **🤖 AI-Powered Itinerary Generation** - Custom itinerary generation using OpenRouter API
- **💾 Save & Manage Itineraries** - Authenticated users can save and revisit their travel plans
- **🔐 Role-Based Access Control** - Secure system with MEMBER and ADMIN roles
- **🌐 RESTful API** - Clean and scalable REST endpoints built with Spring Boot
- **📧 Email Services** - User registration and OTP verification via Gmail SMTP
- **🌤️ Weather Integration** - Real-time weather data using Weather API
- **📰 News Integration** - Travel-related news using News API
- **📍 Place Search** - Discover places using Geoapify API

## 🛠️ Tech Stack

**Backend:**
- Spring Boot 3.x
- Java 17+
- Spring Data JPA
- Spring Security
- Maven
- MySQL Database

**Frontend:**
- HTML5
- CSS3
- JavaScript

**External APIs:**
- OpenRouter API (AI Itinerary Generation)
- Weather API (Weather Information)
- News API (Travel News)
- Geoapify API (Place Search)
- Gmail SMTP (Email Service)

## 📁 Project Structure (Eclipse)
```
roam-smart/
├── src/main/java/
│   └── com.jsp.roam_smart/
│       ├── config/                      # Configuration classes
│       ├── controller/                  # REST Controllers
│       ├── dto/                        # Data Transfer Objects
│       ├── exception/                  # Custom Exceptions
│       ├── model/                      # Entity Models (User, Itinerary, etc.)
│       ├── repository/                 # JPA Repositories
│       ├── service/                    # Business Logic Services
│       │   ├── admin/                  # Admin-specific services
│       │   ├── mail/                   # Email services (OTP, Registration)
│       │   ├── search_place/           # Place search services
│       │   ├── weather/                # Weather services
│       │   └── custom_itinerary/       # Itinerary generation
│       └── RoamSmartApplication.java   # Main Spring Boot Application
│
├── src/main/resources/
│   ├── application.properties          # Application Configuration
│   ├── static/                        # Static resources (CSS, JS, images)
│   └── templates/                     # Email templates (OTP, Registration)
│
├── src/test/java/                     # Test cases
├── frontend/                          # Frontend HTML/CSS/JS files
├── target/                           # Compiled classes
├── .mvn/                            # Maven wrapper
├── pom.xml                          # Maven dependencies
└── README.md
```

## 🚀 Getting Started with Eclipse

### Prerequisites
- **Eclipse IDE for Enterprise Java and Web Developers**
- **Java Development Kit (JDK) 17 or higher**
- **MySQL Server** (8.0 or higher)
- **Maven** (Integrated with Eclipse)
- **Spring Tools Suite (STS)** plugin (Recommended)

### Required API Keys
You'll need to sign up and get API keys from:
1. **OpenRouter** - https://openrouter.ai/ (for AI itinerary generation)
2. **Weather API** - https://www.weatherapi.com/ (for weather data)
3. **News API** - https://newsapi.org/ (for news)
4. **Geoapify** - https://www.geoapify.com/ (for place search)
5. **Gmail Account** - For SMTP email service

### Installation Steps

#### 1. **Clone the Repository**
```bash
git clone https://github.com/Mahantesh03/Roamwise.git
```

#### 2. **Import Project into Eclipse**
- Open Eclipse
- `File` → `Import` → `Maven` → `Existing Maven Projects`
- Browse to the `Roamwise` folder
- Select `pom.xml` and click `Finish`
- Wait for Maven to download dependencies

#### 3. **Configure Database**
Create a MySQL database:
```sql
CREATE DATABASE roamwise;
```

Update `src/main/resources/application.properties`:
```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/roamwise
spring.datasource.username=your_mysql_username
spring.datasource.password=your_mysql_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA/Hibernate
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

#### 4. **Configure API Keys**
Update the following in `application.properties`:
```properties
# Email Configuration (Gmail)
spring.mail.username=${MAIL_USERNAME}
spring.mail.password=${MAIL_PASSWORD}

# Weather API
weather.api.key=${WEATHER_API_KEY}

# News API
newsapi.key=${NEWS_API_KEY}

# OpenRouter API (AI)
openrouter.api.key=${OPENROUTER_API_KEY}

# Geoapify API (Places)
geoapify.api.key=${GEOAPIFY_API_KEY}
```

**Option 1: Set Environment Variables** (Recommended)
- Right-click project → `Run As` → `Run Configurations`
- Select your application
- Go to `Environment` tab
- Add variables: `MAIL_USERNAME`, `MAIL_PASSWORD`, `WEATHER_API_KEY`, etc.

**Option 2: Directly in application.properties**
Replace `${...}` placeholders with actual API keys:
```properties
spring.mail.username=your_email@gmail.com
spring.mail.password=your_app_password
weather.api.key=your_weather_api_key
newsapi.key=your_news_api_key
openrouter.api.key=your_openrouter_key
geoapify.api.key=your_geoapify_key
```

#### 5. **Update Maven Dependencies**
- Right-click on project → `Maven` → `Update Project`
- Check `Force Update of Snapshots/Releases`
- Click `OK`

#### 6. **Run the Application**
- Navigate to `RoamSmartApplication.java`
- Right-click → `Run As` → `Spring Boot App`
- Or: Right-click → `Run As` → `Java Application`

#### 7. **Access the Application**
Open browser and go to: **http://localhost:8080**

## 🔧 Configuration Details

### Email Configuration (Gmail)
To use Gmail SMTP, you need to:
1. Enable 2-Factor Authentication on your Google Account
2. Generate an **App Password**: https://myaccount.google.com/apppasswords
3. Use the App Password (not your regular Gmail password)

Configuration in `application.properties`:
```properties
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your_email@gmail.com
spring.mail.password=your_16_digit_app_password
spring.mail.properties.mail.smtp.auth=true
spring.mail.properties.mail.smtp.starttls.enable=true
```

### Security Configuration
- Default security is set to `DEBUG` mode
- Change to production settings before deployment
- User roles: MEMBER, ADMIN

## 📝 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register new user with email verification |
| POST | `/api/auth/login` | User login |
| POST | `/api/auth/verify-otp` | Verify OTP for registration |
| GET | `/api/itinerary` | Get saved itineraries |
| POST | `/api/itinerary/generate` | Generate AI-powered itinerary |
| GET | `/api/places/search?query={place}` | Search for places |
| GET | `/api/weather?location={city}` | Get weather information |
| GET | `/api/news?category=travel` | Get travel news |

## 🐛 Common Issues & Solutions

### 1. **Port 8080 Already in Use**
Change port in `application.properties`:
```properties
server.port=8081
```

### 2. **Database Connection Error**
- Verify MySQL is running
- Check username/password in `application.properties`
- Ensure database `roamwise` exists

### 3. **Email Sending Failed**
- Use Gmail App Password (not regular password)
- Enable "Less secure app access" or use App Password
- Check firewall settings

### 4. **API Key Errors**
- Verify all API keys are valid and active
- Check API rate limits
- Ensure environment variables are set correctly

### 5. **Maven Dependencies Not Downloading**
- Check internet connection
- Update Maven: Right-click project → Maven → Update Project
- Clean build: Project → Clean

## 📦 Key Dependencies (pom.xml)

- Spring Boot Starter Web
- Spring Boot Starter Data JPA
- Spring Boot Starter Security
- Spring Boot Starter Mail
- MySQL Connector Java
- Lombok (optional)
- Spring Boot DevTools

## 💡 Eclipse Tips for Development

| Shortcut | Action |
|----------|--------|
| `Ctrl + Shift + O` | Organize imports |
| `Ctrl + Shift + F` | Format code |
| `Ctrl + Space` | Auto-complete |
| `Alt + Shift + R` | Rename |
| `Ctrl + /` | Toggle comment |
| `Ctrl + 1` | Quick fix suggestions |

## 👥 Contributors

- **Mahantesh03** - Developer & Maintainer
- Original inspiration: [roam-smart](https://github.com/1sanji1/roam-smart) by 1sanji1

## 📄 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions are welcome! Please follow these steps:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/NewFeature`)
3. Commit changes (`git commit -m 'Add NewFeature'`)
4. Push to branch (`git push origin feature/NewFeature`)
5. Open a Pull Request

## 📧 Support

For issues or questions:
- Open an issue on GitHub
- Contact: [@Mahantesh03](https://github.com/Mahantesh03)

## 🔒 Security Note

**Never commit API keys or passwords to Git!**
- Use environment variables
- Add `application.properties` to `.gitignore` if it contains sensitive data
- Use `.env` files for local development (not committed)

---

⭐ **If you find this project useful, please give it a star!**

**Project Status:** Active Development 🚀
