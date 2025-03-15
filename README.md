# Proxmox AI Manager 

A powerful AI-driven system for managing Proxmox Virtual Environment (PVE) infrastructure, leveraging LLMs for intelligent automation and management assistance.

## Features 

- Natural language processing for Proxmox management
- Command history with vector embeddings
- Intelligent automation with LLM assistance
- Context-aware command suggestions
- Script template management
- VM, container, and cluster operations
- Backup and restore management
- Automated configuration management
- Resource monitoring and analysis
- PostgreSQL database with vector search
- Docker containerization for easy deployment
- Ansible integration for configuration management

## Quick Start

### Prerequisites

- Python 3.9+
- Docker and Docker Compose (for containerized deployment)
- PostgreSQL with pgvector extension
- Proxmox VE environment
- Ansible (for configuration management)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ai-Ev1lC0rP/proxmox-nlp.git
   cd proxmox-nlp
   ```

2. Create and configure the environment variables:
   ```bash
   cp .env.example .env
   # Edit .env with your configurations
   ```

3. Run with Docker Compose:
   ```bash
   docker-compose up -d
   ```

4. Or install manually:
   ```bash
   pip install -r requirements.txt
   python proxmox_ai.py
   ```

## Ansible Integration

The system integrates with Ansible for automated configuration management of Proxmox environments:

### Playbooks

- **proxmox_vm_manager.yml**: Create, start, stop, and manage VMs
- **proxmox_container_manager.yml**: Manage LXC containers
- **proxmox_cluster_manager.yml**: Configure and manage Proxmox clusters
- **proxmox_backup_manager.yml**: Create, restore, and schedule backups

### Command Line Interface

```bash
# List available playbooks
python proxmox_helpers/ansible_cli.py list

# Run VM operations
python proxmox_helpers/ansible_cli.py vm --operation create --vm-name test-vm --memory 2048 --cores 2

# Run container operations
python proxmox_helpers/ansible_cli.py ct --operation create --hostname test-ct --memory 1024

# Manage backups
python proxmox_helpers/ansible_cli.py backup --operation create --vm-id 100 --storage local
```

## Usage

Interact with the AI assistant using natural language commands:

```
# Start the assistant
python proxmox_ai.py

> Create a new VM with 2GB RAM and 2 CPU cores
> List all running containers
> Backup VM 100 to local storage
> Create a weekly backup schedule for all VMs
```

## Architecture

### Components

1. Proxmox API client
2. Command handler
3. Script manager
4. Database manager
5. Ansible manager
6. LLM integration

### Database Schema

The system uses PostgreSQL with the pgvector extension for storing:

1. Command history with vector embeddings
2. Script templates and metadata
3. Session context

## Test Results 

The following tests are currently passing:

### Test Database Manager
- ✅ Test connection to database
- ✅ Test create tables
- ✅ Test create command
- ✅ Test get command by ID
- ✅ Test list commands
- ✅ Test update command
- ✅ Test delete command
- ✅ Test vector search

### Test Command Handler
- ✅ Test parse command
- ✅ Test execute command
- ✅ Test command history
- ✅ Test command suggestions
- ✅ Test vector similarity search

### Test Script Manager
- ✅ Test create script
- ✅ Test get script by ID
- ✅ Test list scripts
- ✅ Test update script
- ✅ Test delete script
- ✅ Test execute script
- ✅ Test script parameters
- ✅ Test script suggestions

## Current Features

- Natural language understanding for Proxmox operations
- Automated VM and container management
- Intelligent error handling and suggestions
- Context-aware command history
- Script template creation and management
- Vector-based semantic search for commands and scripts
- Docker and Docker Compose support for containerized deployment
- CLI interface for executing commands against Proxmox VE
- Ansible integration for configuration management

## Next Steps 

- Terraform module integration for infrastructure as code
- Web dashboard for visualizing Proxmox resources
- Notification system for alerts and events
- Enhanced security features for credential management
- Performance analytics dashboard
- Advanced agent specializations for different management tasks

## License 

MIT License

## Acknowledgments 🙏

This project was inspired by and builds upon several excellent open-source projects:

- [Proxmoxer](https://github.com/proxmoxer/proxmoxer) - Python client for Proxmox API
- [Ansible](https://github.com/ansible/ansible) - IT automation platform
- [Ollama](https://github.com/ollama/ollama) - Run LLMs locally
- [Sentence Transformers](https://github.com/UKPLab/sentence-transformers) - For vector embeddings
- [SQLAlchemy](https://github.com/sqlalchemy/sqlalchemy) - Python SQL toolkit and ORM
- [pgvector](https://github.com/pgvector/pgvector) - Vector similarity search for PostgreSQL

Special thanks to all the contributors and maintainers of these projects for making this work possible!