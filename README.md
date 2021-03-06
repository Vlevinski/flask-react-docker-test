# React + Flask Development Boilerplate

## Overview
Extremely lightweight development environment for a web application
running a [React](https://reactjs.org/) front-end and 
[Flask](http://flask.pocoo.org/) API back-end. The 
front-end connects to the back-end by making HTTP requests for
desired data. React and Flask are containerized and managed with 
[Docker Compose](https://docs.docker.com/compose/).

### Why Create React App?
[Create React App](https://facebook.github.io/create-react-app/) allows 
us to very easily *create a React app* with no build configuration. 

### Why Flask?
Flask is a lightweight, highly-customizable micro-framework for Python. 
   (http://flask.pocoo.org/docs/1.0/quickstart/#a-minimal-application)).
.

### Why Docker Compose?
[Docker](https://www.docker.com/) maintains software and all of its dependencies within a "container",
which can make collaborating and deploying simpler. [Docker Compose](https://docs.docker.com/compose/)
is a tool for easily managing applications running multiple Docker containers. 

## How to Use
    
This spins up Compose and builds a local development environment according to 
our specifications in [docker-compose.yml](docker-compose.yml). Keep in mind that 
this file contains settings for *development*, and not *production*.

After the containers have been built (this may take a few minutes), run

    docker-compose up --build
    
This one command boots up a local server for Flask (on port 5000)
and React (on port 3000). Head over to

    http://localhost:3000/ 
    
to view an incredibly underwhelming React webpage listing two fruits and their
respective prices. 
Though the apparent result is underwhelming, this data was retrieved through an API call
 to our Flask server, which can be accessed at

    http://localhost:5000/api/v1.0/test
    
The trailing '*/api/v1.0/test*' is simply for looks, and can be tweaked easily
in [api/app.py](api/app.py). The front-end logic for consuming our API is
contained in [client/src/index.js](client/src/index.js). The code contained within
these files simply exists to demonstrate how our front-end might consume our back-end
API.

Finally, to gracefully stop running our local servers, you can run
 
    docker-compose down

in a separate terminal window or press __control + C__.


## License
Feel free to use the code in this repository however you wish. Details are provided in
[LICENSE.md](LICENSE.md).


