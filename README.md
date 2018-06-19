# SQLI Test

In this example, I set up a flask server, listening on port 5000, which launchs a tiny python app which counts how many times you have visited the website. I also created a nginx reverse proxy, published on port 8000 which publish the container's app on port 5000.

# Installation and running
You just need to untar the package and call the docker-compose command.

    tar zxvf compose.tgz
    cd compose
    docker-compose up -d
    
It will build and download all necessary images and will start the three containers: the redis database, the nginx reverse proxy and the alpine image with the flask app.
# Stopping the app
In order to stop the application, from the main folder, you need to execute
`docker-compose stop`
# Removing the app
To completely remove the app and all related containers
`docker-compose down`

# Configuring
If you need to configure the nginx proxy you only will need to modify the `nginx/default.conf` file. The flask application is located on the `app.py` file on the root directory. Any extra requirements should be added on the `requirements.txt`file
After making any changes, you need to run again `docker-compose up -d` to rebuild the changes.

