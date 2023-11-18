# Docker-WebDAVServer

## Introduction

Il s'agit d'un dépôt pour configurer un serveur WebDAV à l'aide de Docker.

## Prerequisites

Avant de commencer, assurez-vous que les éléments suivants sont installés :

- Docker
- Docker Compose

## Usage

Pour utiliser ce référentiel, procédez comme suit :

1. Cloner le dépôt:

    ```bash
    git clone https://github.com/your-username/Docker-WebDAVServer.git
    ```

2. Accédez au répertoire cloné:

    ```bash
    cd Docker-WebDAVServer
    ```

3. Ajouté un utilisateur

    ```bash
    sudo htdigest .webdav/apache2/htpasswd/users.password {realm} {user}
    ```

4. Démarrez le serveur WebDAV:

    ```bash
    docker-compose up -d
    ```
