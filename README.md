# Dell EMC ecscli
Manage Elastic Cloud Storage (ECS) resources with the ECS command line interface (CLI)

To run:

    # docker pull kevkha/ecscli
    # mkdir -p ~/ecscli/config
    # docker run -td --restart=always --net=host --name dellemc-ecscli -v /root/ecscli/config:/root kevkha/ecscli
    # docker exec -it dellemc-ecscli ecscli --version
