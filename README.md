# Doctor Appointment System

A microservices-based test application that displays doctors and their appointments through a web interface.

## Architecture

The system consists of three main microservices:

- **Frontend**: Node.js web application that provides the UI (**port 3000**)
- **Doctors Service**: Python Flask API that manages doctor information (**port 9090**)
- **Appointments Service**: Python Flask API that manages appointment data (**port 7070**)
- **Database**: MySQL instance for data persistence (**port 3306**)

## Features

- View list of doctors with their specialties
- View appointments with ratings
- Tab-based navigation between doctors and appointments views
- Containerized microservices architecture
- Kubernetes deployment support
- Automated CI/CD pipelines

## Prerequisites

Ensure you have the following installed:

- **Docker**
- **Docker Compose**
- **Kubernetes cluster** (optional)
- **Node.js** 14+
- **Python** 3.9+

## Running Locally

### Using Docker Compose
Run the following command:

```bash
docker compose up
```

The application will be available at:

- **Frontend**: [http://localhost:3000](http://localhost:3000)
- **Doctors API**: [http://localhost:9090](http://localhost:9090)
- **Appointments API**: [http://localhost:7070](http://localhost:7070)

## ☸ Kubernetes Deployment

Apply the Kubernetes manifests:

```bash
kubectl apply -f db/k8s/app.yml
kubectl apply -f doctors/k8s/app.yaml
kubectl apply -f appointments/k8s/app.yaml
kubectl apply -f frontend/k8s/app.yaml
```

## API Endpoints

### Doctors Service
- `GET /doctors` - List all doctors
- `GET /doctor/<id>` - Get doctor by ID
- `GET /health` - Health check

### Appointments Service
- `GET /appointments` - List all appointments
- `GET /appointment/<id>` - Get appointment by ID
- `GET /health` - Health check

## CI/CD

The project uses **GitHub Actions** workflows for automated builds and deployments:

- Automatic **Docker image builds** on code changes
- Automated updates to `docker-compose.yml`
- Separate pipelines for each microservice
