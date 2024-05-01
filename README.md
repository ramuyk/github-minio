# Introduction

This repository provides a `docker-compose.yml` ready-to-use Docker configuration to simplify the deployment of the official MinIO Docker container. MinIO is a high-performance object storage solution that is API compatible with Amazon S3. For comprehensive details about extra configurations and advanced setup options, please refer to the [MinIO official DockerHub documentation](https://hub.docker.com/r/minio/minio).

## Repository Contents

This repository includes:

- **Docker Compose File**: A `docker-compose.yml` file that configures the MinIO Docker container. Highlights of this setup include:
  - **Persistent Data Storage**: Configures a volume:
    - `minio_data` at `/data` for storing MinIO data.
  
    This setup ensures that your MinIO data is preserved when the container is restarted.

## Getting Started

### Important Preliminary Steps

Before starting the quick setup, please note the following adjustments:

1. **Important Note on Port Mapping**: The `docker-compose.yml` file contains port mappings to `127.0.0.1`, limiting access to the localhost only. To make the service accessible from other machines or publicly, change the IP address in the port mapping. For instance, use `0.0.0.0` to bind to all network interfaces, updating the ports line to `- "0.0.0.0:10100:9000"` and `- "0.0.0.0:10101:9001"` for broader network access.

### Quick Setup

1. **Clone the Repository**:
   Clone this repository to your local machine using the following Git command:
   ```bash
   git clone https://github.com/ramuyk/docker-minio.git
   cd docker-minio
   ```

2. **Start MinIO**:
   Use the following command to build the MinIO image and start the service:
   ```bash
   docker compose up -d
   ```

3. **Access MinIO**:
   Open a web browser and navigate to `http://localhost:10101` to access the MinIO web interface. Log in with the root credentials provided in the Docker Compose file:
   - **Username**: admin
   - **Password**: minioadmin

   It is strongly recommended to change these credentials immediately after your first login for security reasons.
