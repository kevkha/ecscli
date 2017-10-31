# Dell EMC ecscli
Manage Elastic Cloud Storage (ECS) resources with the ECS command line interface (CLI)

To run:

    # docker pull kevkha/ecscli
    # mkdir -p ~/ecscli/config
    # docker run -td --restart=always --name dellemc-ecscli -v /root/ecscli/config:/root kevkha/ecscli
    # docker exec -it dellemc-ecscli ecscli --version

Configure the ECS CLI:

The folllowings commands are executed inside the container.

    # docker exec -it dellemc-ecscli sh
    / # ecscli config -pf demoprofile
    / # ecscli config list
    / # ecscli config set -pf demoprofile
    / # ecscli config delete -pf demoprofile
    
Authenticate a profile:

    / # ecscli authenticate
