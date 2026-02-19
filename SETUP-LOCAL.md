# Global AI AgentCamp - Building AI Agents with Microsoft Foundry and the AI Toolkit

Steps to set up the local environment for the Global AI AgentCamp workshop.

## Prerequisites

- **Python >3.12+**: Ensure you have Python installed.
- **Docker**: Install Docker to run the PostgreSQL database and other services.
- **Docker Compose**: Install Docker Compose to manage multi-container applications.
- **Visual Studio Code**: Install VS Code for development and use the AI Toolkit extension.

### Install Python Dependencies

Upgrade `pip` and `wheel` to ensure you have the latest versions:
```bash
pip install -U pip wheel
```

Install both the `python` and `data` dependencies:
```bash
pip install -r requirements-dev.txt
```

## Database

### Docker

From the project root directory, run the following command to start the PostgreSQL database using Docker Compose:
```bash
docker-compose up
```
add `-d` to run the containers in detached mode:
```bash
docker-compose up -d
```

This will start the PostgreSQL database used by the Visual Studio Code dev container and the MCP server. 

### Data Injection

To populate the database with sample data, follow this detailed guide: [data/database/README.md](./data/database/README.md):

Here are the summarized steps to inject data into the PostgreSQL database:
```bash
cd data/database
```
then run the following command to execute the data injection script:
```bash
POSTGRES_HOST='127.0.0.1' python generate_zava_postgres.py
```

### Access

The database will be accessible at `127.0.0.1:5432` with the credentials specified [in this file](./data/database/README.md). The `db` host will be used for connections from within the dev container and MCP server.


## Visual Studio Code Dev Container

Run `> Dev Containers: Rebuild and Reopen in Container` from the command palette to start the Visual Studio Code dev container. This will set up a development environment with all necessary dependencies and configurations for the workshop.