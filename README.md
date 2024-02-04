# fowardauth-traefik-docker-compose

# Secure Services with OIDC and Traefik Forward Auth

## Overview

This repository demonstrates securing upstream services using OpenID Connect (OIDC) login with Traefik and `thomseddon/traefik-forward-auth`. It provides a practical example of how to implement authentication in a microservices architecture, ensuring that access to services is protected and authenticated via a trusted OIDC provider.

## Why OIDC with Traefik Forward Auth?

Integrating OIDC with Traefik using `traefik-forward-auth` allows for a secure, scalable, and easy-to-implement authentication mechanism. This setup is ideal for protecting sensitive services behind an authentication layer, ensuring that only authorized users can access them.

## Prerequisites

- Docker and Docker Compose installed on your system
- An OIDC-compatible identity provider (e.g., Keycloak) configured

## Configuration

Update the `.env` file or set environment variables directly in `docker-compose.yaml` for the `traefik-forward-auth` service:

- `PROVIDERS_OIDC_ISSUER_URL`: Your OIDC provider's URL.
- `PROVIDERS_OIDC_CLIENT_ID` and `PROVIDERS_OIDC_CLIENT_SECRET`: Obtained from your OIDC provider.
- `SECRET`: A random secret used by `traefik-forward-auth`.

## Running the Project

1. Clone this repository:

```bash 
git clone <repository-url>
```

2. Navigate to the project directory:

```bash
cd <project-directory>
```

3. Start the services:

```bash
docker-compose up -d
```

## Access Control

Access to the `echo-server` service is protected by OIDC authentication. Users are redirected to the OIDC provider for login before accessing the service.

## Contributing

Contributions to improve the project are welcome. Feel free to fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
