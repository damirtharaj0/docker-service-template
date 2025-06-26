# Docker Service Template

This is a template repository for creating new microservices in Docker-based projects. It provides a standardized structure and configuration that ensures consistency across all services in your project.

## Overview

This template is designed to be used with the [Docker Project Template](https://github.com/damirtharaj0/docker-project-template) which includes an automated script (`add_service.sh`) to generate new services from this template.

## Template Structure

```
.
├── Dockerfile              # Base Docker configuration
├── app/                    # Your application code goes here
│   └── .gitkeep           # Keeps the app directory in git
└── README.md              # This file
```

## Features

- 🐳 **Alpine Linux Base**: Lightweight and secure base image
- 📁 **Organized Structure**: Clear separation between configuration and application code
- 🔧 **Development Ready**: Optimized for development with volume mounting
- 🚀 **Quick Setup**: Ready to use with minimal configuration
- 📦 **Consistent**: Ensures all services follow the same structure

## Getting Started

### Using with Docker Project Template (Recommended)

This template is meant to be used with the [Docker Project Template](https://github.com/damirtharaj0/docker-project-template):

1. Clone the main project template:
   ```bash
   git clone https://github.com/damirtharaj0/docker-project-template my-project
   cd my-project
   ```

2. Create a new service using this template:
   ```bash
   ./add_service.sh my-service-name
   ```

### Manual Usage

If you want to use this template manually:

1. Clone this repository:
   ```bash
   git clone https://github.com/damirtharaj0/docker-service-template my-service
   cd my-service
   ```

2. Add your application code to the `app/` directory

3. Customize the `Dockerfile` if needed

## Dockerfile Configuration

The included `Dockerfile` provides:

- **Base Image**: Alpine Linux for minimal footprint
- **Working Directory**: `/app` inside the container
- **File Copy**: Copies everything from `./app` to the container's `/app` directory

### Customizing the Dockerfile

You can modify the `Dockerfile` to suit your specific needs:

- Change the base image (e.g., `FROM node:alpine`, `FROM python:alpine`)
- Add package installations
- Set environment variables
- Configure expose ports
- Add custom commands

## Application Development

1. **Add your code**: Place all your application files in the `app/` directory
2. **Dependencies**: Include package managers files (package.json, requirements.txt, etc.) in the `app/` directory
3. **Configuration**: Add any configuration files your application needs
4. **Assets**: Include static files, templates, or other resources in the `app/` directory

## Integration with Docker Compose

When used with the Docker Project Template, services created from this template are automatically configured in `docker-compose.yml` with:

- Volume mounting for live development
- Interactive terminal support
- Proper service naming and networking

## Best Practices

- Keep the `app/` directory clean and organized
- Use environment variables for configuration
- Follow the principle of one service per container
- Include a `.dockerignore` file if needed to exclude unnecessary files
- Document any specific setup requirements in your service's README

## Development Workflow

1. Create service from template
2. Develop in the `app/` directory
3. Test with `docker compose up <service-name>`
4. Iterate and refine
5. Deploy when ready

## Related Projects

- [Docker Project Template](https://github.com/damirtharaj0/docker-project-template) - Main project template that uses this service template
