# Self-Hosted N8N with External Ollama for Mac

This repository provides a Docker Compose configuration for running N8N with an external Ollama instance on macOS.

## Prerequisites

- Docker Desktop for Mac
- [Ollama](https://ollama.com/) installed and running on your Mac

## Ollama Setup 

1. Install Ollama on your Mac
   ```bash
   brew install ollama
   ```

## Self-hosted n8n for Mac

**Self-hosted n8n for Mac** is an open-source Docker Compose template designed to quickly set up a local n8n environment that integrates with the Ollama service, specifically optimized for Mac users.

![n8n.io - Screenshot](https://raw.githubusercontent.com/n8n-io/self-hosted-ai-starter-kit/main/assets/n8n-demo.gif)

### Overview

This project combines the self-hosted n8n platform with the Ollama service, allowing you to build and run AI workflows locally on your Mac. It is designed to facilitate the development of low-code applications that leverage AI capabilities.

### What’s included

✅ **Self-hosted n8n** - A low-code platform with over 400 integrations and advanced AI components.

✅ **Qdrant** - An open-source, high-performance vector store with a comprehensive API.

✅ **PostgreSQL** - The workhorse of the Data Engineering world, handling large amounts of data safely.

### Installation

#### Cloning the Repository

```bash
git clone https://github.com/yourusername/self-hosted-n8n-mac.git
cd self-hosted-n8n-mac
```

#### Setting up Environment Variables

Before running n8n, you need to set up your environment variables:

1. Copy the example environment file to create your .env file:
   ```bash
   cp .env.example .env
   ```

2. Open the .env file in your preferred text editor:
   ```bash
   nano .env
   # or
   open -a TextEdit .env
   ```

3. Update the following variables as needed:
   - `POSTGRES_PASSWORD`: Set a strong password for your PostgreSQL database
   - `POSTGRES_NON_ROOT_PASSWORD`: Set a password for the non-root PostgreSQL user
   - `N8N_ENCRYPTION_KEY`: Set a secure random string for encrypting credentials
   - `N8N_USER_MANAGEMENT_JWT_SECRET`: Set a secure random string for JWT secret
   - `OLLAMA_HOST`: Set to your local Ollama instance (default: http://host.docker.internal:11434)

4. Save the file after making your changes.

> **Note**: Generating a secure encryption key is crucial. You can use a command like `openssl rand -hex 24` to generate a random key.

#### Running n8n using Docker Compose

For Mac users, you can run the starter kit as follows:

```bash
docker compose up
```

### Environment Variables

Make sure to configure your environment variables by copying `.env.example` to `.env` and updating the values as needed.

### Quick Start and Usage

1. Open <http://localhost:5678/> in your browser to set up n8n. You’ll only have to do this once.
2. Open the included workflow: <http://localhost:5678/workflow/srOnR8PAY3u4RSwb>
3. Click the **Chat** button at the bottom of the canvas to start running the workflow.

### Upgrading

To upgrade your setup, run:

```bash
docker compose pull
docker compose create && docker compose up
```

### License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

### Support

Join the conversation in the [n8n Forum](https://community.n8n.io/) for support, sharing your work, and proposing ideas for improvements.