# Docker & Docker-Compose Cheat Sheet

This file contains a list of essential Docker commands with descriptions, tailored for this project.

---

### Managing Your Application (The most common commands)

*   **`docker-compose build`**
    *   **What it does:** Builds or rebuilds the images for your `frontend` and `backend` services based on their `Dockerfile`.
    *   **When to use it:** After you change your source code, add a new dependency, or modify a `Dockerfile`.

*   **`docker-compose up`**
    *   **What it does:** Starts your entire application (both frontend and backend containers). It will show all the logs directly in your terminal.
    *   **When to use it:** When you want to start your app and watch the logs live. Press `Ctrl+C` to stop it.

*   **`docker-compose up -d`**
    *   **What it does:** Starts your entire application in "detached" mode, meaning it runs in the background.
    *   **When to use it:** This is the most common way to run your app. You get your terminal back after starting it.

*   **`docker-compose down`**
    *   **What it does:** Stops and removes the containers, and removes the network created for your application.
    *   **When to use it:** When you are finished working and want to completely stop your application.

### Viewing Information & Logs

*   **`docker-compose ps`**
    *   **What it does:** Shows the status of your application's containers (e.g., if they are running, stopped, or have errors). `ps` stands for "processes".
    *   **When to use it:** To get a quick check on your app's state.

*   **`docker-compose logs`**
    *   **What it does:** Shows the logs from all services in your application.
    *   **When to use it:** To see what has happened in your application, especially if something isn't working.

*   **`docker-compose logs -f <service_name>`**
    *   **What it does:** Follows the live, real-time logs from a specific service. Replace `<service_name>` with `frontend` or `backend`.
    *   **When to use it:** When you want to watch the logs of a specific service as you interact with the app. Example: `docker-compose logs -f frontend`.

### Cleaning Up Your System

*   **`docker images`**
    *   **What it does:** Lists all the Docker images stored on your computer.
    *   **When to use it:** To see how much space your images are taking up.

*   **`docker system prune`**
    *   **What it does:** A cleanup command that removes all stopped containers, unused networks, and "dangling" images (layers that are no longer referenced by any image).
    *   **When to use it:** Periodically to reclaim disk space. It will ask for confirmation before deleting anything.

### Debugging (Advanced)

*   **`docker exec -it <container_name> /bin/sh`**
    *   **What it does:** Opens a command-line shell *inside* a running container. You can get the `<container_name>` from the `docker-compose ps` command.
    *   **When to use it:** For advanced debugging. If you need to look at the files inside a running container to see what's going on. Remember the principle of immutability: use this for looking around, not for changing things.
