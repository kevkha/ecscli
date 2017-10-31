# Dell EMC ecscli
Manage Elastic Cloud Storage (ECS) resources with the ECS command line interface (CLI)

# Pull docker image

    # docker pull kevkha/ecscli

# Create config directory on host

Linux/Mac:

    # mkdir -p $HOME/ecscli/config

Windows:

    # mkdir %userprofile%\ecscli\config
    

# Start container

Linux/Mac:

    # docker run -td --restart=always --name dellemc-ecscli -v $HOME/ecscli/config:$HOME kevkha/ecscli

Windows:

    # docker run -td --restart=always --name dellemc-ecscli -v %userprofile%\ecscli\config:$HOME kevkha/ecscli

# Enter container shell

    # docker exec -it dellemc-ecscli sh

# Configure the ECS CLI

    / # ecscli --version
    / # ecscli config -pf demoprofile
    / # ecscli config list
    / # ecscli config set -pf demoprofile
    / # ecscli config delete -pf demoprofile
    
# Authenticate a profile

    / # ecscli authenticate
