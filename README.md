# Docker gitea mariadb 

### Prerequisites

In order to use this compose file (docker-compose.yml) you must have:

1. docker [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)
2. docker-compose [https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)
3. docker-compose-letsencrypt-nginx-proxy-companion [https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion](https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion)


### Getting started

1. Clone project :

    ```sh
    git clone https://github.com/rgarofalo/docker-gitea-mariadb
    ```

2. You could customize your settings before installation :

    Edit `.env` file

3. Install :

    ```sh
    # Copy the configuration file from the dist file
    cp etc/app.ini.dist etc/app.ini

    # Start services
    sudo docker-compose up -d

    # Copy the configuration file to the container
    sudo docker cp $(pwd)/etc/app.ini $(sudo docker-compose ps -q gitea-app):/data/gitea/conf/app.ini

    sudo docker cp $(pwd)/etc/templates $(sudo docker-compose ps -q gitea-app):/data/gitea/

    # Restart the server to reload the configuration
    sudo docker-compose restart gitea-app

    ```