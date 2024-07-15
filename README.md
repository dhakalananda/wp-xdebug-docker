# Debug your WordPress Docker instance with XDebug

What does this repository offer?

- A fully debuggable WordPress docker instance
- Limit of upload_max_filesize increased to upload plugins with high filesize

## Steps to Installation

1. `git clone https://github.com/dhakalananda/wp-xdebug-docker`
2. `cd wp-xdebug-docker`
3. `docker-compose up -d`
4. Navigate to http://localhost:8000 and set up WordPress

XDebug is listening on port 9000. Use your preferred IDE to attach to the listener.

### For Windows

- Remove the line `- ./wp:/var/www/html` from the `docker-compose.yaml` file

### For MacOS

For some Mac devices, using the docker-compose might install AMD version so:

1. `git clone https://github.com/Automattic/wordpress-xdebug`
2. `cd wordpress-xdebug`
3. `docker build -t wp-debug:latest .`
4. `cd`
5. `git clone https://github.com/dhakalananda/wp-xdebug-docker`
6. `cd wp-xdebug-docker`
7. Replace the `image: automattic/wordpress-xdebug:latest` with `image: wp-debug:latest` in the docker-compose.yaml file
8. `docker-compose up -d`
9. Navigate to http://localhost:8000 and set up WordPress

### Attaching with VSCode:

1. Install Dev Container & PHP Debug VSCode plugin
2. Use the Connect to option and Attach to running container
3. Select the WordPress container
4. Create a launch.json file and attach to 9000 port

Example launch.json file:
```json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Listen for Xdebug",
            "type": "php",
            "request": "launch",
            "port": 9000
        }
        
    ]
}
   ```

For more info: https://code.visualstudio.com/docs/devcontainers/attach-container

This repo makes use of https://github.com/Automattic/wordpress-xdebug image
