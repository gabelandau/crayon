# Crayon
Crayon is a Docker Stack that emulates a LAMP stack, designed to be used for local development. It uses three Docker images: php-apache, mysql, and phpmyadmin.

Since this is used for development, it uses the latest versions of the images. This may cause configuration issues, so it is not meant to be used in a production environment (though it could be easily tweaked to do so).

## Using Crayon
To run crayon, clone the git repository (or download the zip) and rename the folder to the name of your project. Then, follow the steps below:
1. Copy your applications source code to the `html` folder in this repository.
2. Rename the containers that the docker-compose file will create, if you wish. This is useful if you want multiple mysql servers to host different data.
3. Open a terminal window, navigate to this repository on your computer, and run `docker-compose build`
4. To start the containers, run `docker-compose up` (add a `-d` to run detached)
5. If you ran without `-d`, press `ctrl-c` to quit the application, or `docker-compose stop` if you ran detached

## Accessing Your Application
Navigate your browser to `localhost:8000` to see it run!

Navigate to `localhost:8080` to visit the phpMyAdmin installation for your site. The credentials to login are `root` `root`

## Notes
If you want to have more than one instance of Crayon running at a time, you must change the ports and container names in `docker-compose.yml` and the `Dockerfile` of the php container. 
