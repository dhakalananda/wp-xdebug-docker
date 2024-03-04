For some Mac devices, using the docker-compose might install AMD version so:

1. `git clone https://github.com/Automattic/wordpress-xdebug`
2. `cd wordpress-xdebug`
3. `docker build -t wp-debug:latest .`
4. Use the `image: wp-debug:latest` in the docker-compose.yaml file
5. `docker-compose up -d`
