# Installing docker on a Raspberry PI

    curl -sSL https://get.docker.com | sh
    sudo usermod -aG docker $USER
    logout

to check if docker installed:

    docker run hello-world