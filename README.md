<div align="center">

# 🐳 Flask Calculator - Dockerized Web Application

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

*A modern, containerized web calculator built with Flask and Docker for seamless deployment anywhere*

[Features](#-features) • [Quick Start](#-quick-start) • [Documentation](#-documentation) • [Contributing](#-contributing)

</div>

---

## 📖 Overview

**Custom-images-with-Docker** demonstrates the power of containerization by packaging a Flask-based calculator web application with all its dependencies into a custom Docker image. This project showcases best practices in modern application deployment, ensuring consistency across development, testing, and production environments.

### 🎯 Why This Project?

- **🔒 Consistency**: Same behavior across all environments
- **🚀 Fast Deployment**: Deploy in seconds, anywhere Docker runs
- **📦 Self-Contained**: All dependencies bundled together
- **♻️ Reproducible**: Build once, run everywhere
- **🔧 Easy Scaling**: Horizontal scaling made simple

---

## ✨ Features

<table>
<tr>
<td width="50%">

### 🧮 Calculator Features
- ➕ Addition
- ➖ Subtraction
- ✖️ Multiplication
- ➗ Division
- 🎨 Clean, responsive UI
- ⚡ Real-time calculations

</td>
<td width="50%">

### 🐳 Docker Features
- 📦 Custom Docker image
- 🔄 Multi-stage optimization
- 🌐 Port mapping (8080)
- 🔐 Production-ready setup
- 📊 Lightweight (slim-buster)
- 🚀 Ready for cloud deployment

</td>
</tr>
</table>

---

## 🚀 Quick Start

### Prerequisites

Before you begin, ensure you have the following installed:
- [Docker](https://docs.docker.com/get-docker/) (version 20.10 or higher)
- [Docker Hub Account](https://hub.docker.com/) (for pushing images)

### 🏃‍♂️ Running the Application

#### Option 1: Using Pre-built Image (Recommended)

```bash
# Pull and run the image from Docker Hub
docker pull jimaifsd/calculator:latest
docker run -d -p 8080:8080 --name calculator-app jimaifsd/calculator:latest
```

#### Option 2: Build from Source

```bash
# Clone the repository
git clone https://github.com/NayeemHossenJim/Custom-images-with-Docker.git
cd Custom-images-with-Docker

# Build the Docker image
docker build -t jimaifsd/calculator:latest .

# Run the container
docker run -d -p 8080:8080 --name calculator-app jimaifsd/calculator:latest
```

### 🌐 Access the Application

Once the container is running, open your browser and navigate to:

```
http://localhost:8080
```

🎉 **That's it!** Your calculator app is now running in a Docker container.

---

## 📚 Documentation

### 🏗️ Project Structure

```
Custom-images-with-Docker/
│
├── 📄 app.py                 # Main Flask application
├── 📄 calculator.py          # Calculator class (standalone)
├── 🐳 Dockerfile             # Docker image configuration
├── 📋 requirements.txt       # Python dependencies
├── 📖 README.md              # Project documentation
├── 📜 LICENSE                # MIT License
│
├── 📁 static/                # Static assets
│   ├── main.css             # Main stylesheet
│   └── style.css            # Additional styles
│
└── 📁 templates/             # HTML templates
    ├── index.html           # Homepage
    └── results.html         # Results page
```

### 🛠️ Technology Stack

| Technology | Purpose | Version |
|------------|---------|---------|
| **Python** | Backend Language | 3.10 |
| **Flask** | Web Framework | Latest |
| **Docker** | Containerization | Latest |
| **Gunicorn** | WSGI Server | Latest |
| **HTML/CSS** | Frontend | HTML5/CSS3 |

---

## 🐳 Docker Commands Reference

### Building Images

```bash
# Build with tag
docker build -t jimaifsd/calculator:latest .

# Build with custom tag
docker build -t jimaifsd/calculator:v1.0.0 .

# Build without cache
docker build --no-cache -t jimaifsd/calculator:latest .
```

### Running Containers

```bash
# Run in foreground (see logs)
docker run -p 8080:8080 jimaifsd/calculator:latest

# Run in background (detached mode)
docker run -d -p 8080:8080 --name calculator-app jimaifsd/calculator:latest

# Run with automatic restart
docker run -d -p 8080:8080 --restart unless-stopped jimaifsd/calculator:latest

# Run with environment variables
docker run -d -p 8080:8080 -e FLASK_ENV=production jimaifsd/calculator:latest
```

### Container Management

```bash
# View running containers
docker ps

# View all containers (including stopped)
docker ps -a

# View container logs
docker logs calculator-app

# Follow logs in real-time
docker logs -f calculator-app

# Stop the container
docker stop calculator-app

# Start the container
docker start calculator-app

# Restart the container
docker restart calculator-app

# Remove the container
docker rm calculator-app

# Remove container forcefully
docker rm -f calculator-app
```

### Image Management

```bash
# List all images
docker images

# Remove an image
docker rmi jimaifsd/calculator:latest

# Remove dangling images
docker image prune

# View image details
docker inspect jimaifsd/calculator:latest
```

### Docker Hub Operations

```bash
# Login to Docker Hub
docker login

# Tag an image
docker tag jimaifsd/calculator:latest jimaifsd/calculator:v1.0.0

# Push to Docker Hub
docker push jimaifsd/calculator:latest

# Push specific version
docker push jimaifsd/calculator:v1.0.0

# Pull from Docker Hub
docker pull jimaifsd/calculator:latest
```

---

## 🔧 Development

### Local Development (Without Docker)

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment (Windows)
.\venv\Scripts\activate

# Activate virtual environment (Linux/Mac)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Run the application
python app.py
```

Visit `http://localhost:8080` to see the app.

### 🧪 Testing the Calculator

You can also run the standalone calculator script:

```bash
python calculator.py
```

---

## 🌍 Deployment

### Deploy to Cloud Platforms

<details>
<summary><b>☁️ AWS ECS</b></summary>

```bash
# Push to Amazon ECR
aws ecr get-login-password --region region | docker login --username AWS --password-stdin aws_account_id.dkr.ecr.region.amazonaws.com
docker tag jimaifsd/calculator:latest aws_account_id.dkr.ecr.region.amazonaws.com/calculator:latest
docker push aws_account_id.dkr.ecr.region.amazonaws.com/calculator:latest
```

</details>

<details>
<summary><b>☁️ Google Cloud Run</b></summary>

```bash
# Deploy to Cloud Run
gcloud run deploy calculator \
  --image jimaifsd/calculator:latest \
  --platform managed \
  --region us-central1 \
  --allow-unauthenticated
```

</details>

<details>
<summary><b>☁️ Azure Container Instances</b></summary>

```bash
# Deploy to Azure
az container create \
  --resource-group myResourceGroup \
  --name calculator-app \
  --image jimaifsd/calculator:latest \
  --dns-name-label calculator-app \
  --ports 8080
```

</details>

<details>
<summary><b>☁️ Heroku</b></summary>

```bash
# Deploy to Heroku
heroku container:login
heroku create calculator-app
heroku container:push web
heroku container:release web
```

</details>

---

## 🎨 Customization

### Modify Port

To run on a different port, update the `docker run` command:

```bash
docker run -d -p 3000:8080 jimaifsd/calculator:latest
```

Access at `http://localhost:3000`

### Update Styles

Edit the CSS files in the `static/` directory to customize the look and feel.

### Add New Operations

1. Edit `app.py` to add new calculation routes
2. Update templates in `templates/` directory
3. Rebuild the Docker image

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

### 💡 Ideas for Contribution

- [ ] Add more mathematical operations (power, square root, etc.)
- [ ] Implement calculation history
- [ ] Add unit tests
- [ ] Create CI/CD pipeline
- [ ] Add dark mode theme
- [ ] Implement API endpoints
- [ ] Add Docker Compose for multi-container setup
- [ ] Create Kubernetes deployment files

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Flask team for the amazing web framework
- Docker for revolutionizing application deployment
- Open source community for inspiration

---

## 📞 Contact & Support

<div align="center">

**Nayeem Hossen Jim**

[![GitHub](https://img.shields.io/badge/GitHub-NayeemHossenJim-181717?style=for-the-badge&logo=github)](https://github.com/NayeemHossenJim)
[![Docker Hub](https://img.shields.io/badge/Docker_Hub-jimaifsd-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/u/jimaifsd)

**Found this helpful? Give it a ⭐️!**

</div>

---

<div align="center">

### 🚀 Ready to containerize your applications?

**Start building with Docker today!**

Made with ❤️ by [Nayeem Hossen Jim](https://github.com/NayeemHossenJim)

</div>