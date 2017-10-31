# Dell EMC ecscli in Docker Container
Manage Elastic Cloud Storage (ECS) resources with the ECS command line interface (CLI)

# Pull docker image

    # docker pull kevkha/ecscli
    # docker images

# Create config directory on host
Creating local directory to be mapped inside a container to retain ecscli config files on the local host.

Linux/Mac:

    # mkdir -p $HOME/ecscli/config

Windows:

    # mkdir %userprofile%\ecscli\config
    

# Start container
Always start `dellemc-ecscli` container and map local directory.

Linux/Mac:

    # docker run -td --restart=always --name dellemc-ecscli -v $HOME/ecscli/config:$HOME kevkha/ecscli

Windows:

    # docker run -td --restart=always --name dellemc-ecscli -v %userprofile%\ecscli\config:$HOME kevkha/ecscli

# List running container
```
# docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
17c84daf618c        kevkha/ecscli       "python2"           4 seconds ago       Up 4 seconds                            dellemc-ecscli
```
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

# ECS ecsli usage (as of version 3.1.18)
```
positional arguments:
  {config,authenticate,authentication,baseurl,billing,bucket,cas,datastore,failedzones,keystore,mgmtuserinfo,monitor,nodes,objectuser,objectvpool,nfs,secretkeyuser,system,namespace,varray,vdc_data,vdc,passwordgroup,dashboard,transformation,vdc_keystore,capacity}
                        Use One Of Commands
    config              ecscli profile configuration
    authenticate        Authenticate ECS user
    authentication      Operations on Authentication
    baseurl             Operations on Base URL
    billing             Operations to retrieve ECS billing information
    bucket              Operations on Bucket
    cas                 Operations on CAS profile
    datastore           Operations on datastore
    failedzones         Get failed zone information
    keystore            Operations on keystore
    mgmtuserinfo        Operations on Mgmtuserinfo
    monitor             Get monitoring events for the given time bucket
    nodes               Operations to retrieve ECS datanodes information
    objectuser          Operations on Objectuser
    objectvpool         Operations on ObjectVPool
    nfs                 Operations on NFS
    secretkeyuser       Operations on Secretkeyuser
    system              Operations on system
    namespace           Operations on Namespace
    varray              Operations on varray
    vdc_data            Operations on VirtualDataCenter
    vdc                 Operations on VirtualDataCenter
    passwordgroup       Operations on Passwordgroup
    dashboard           Operations on replication group links
    transformation      Operations on Centera transformation
    vdc_keystore        Operations on vdc keystore certificate
    capacity            Get capacity information

optional arguments:
  -h, --help            show this help message and exit
  -hostname <hostname>, -hn <hostname>
                        Hostname (fully qualifiled domain name) or IPv4
                        address (i.e. 192.0.2.0) or IPv6 address inside quotes
                        and brackets (i.e. "[2001:db8::1]") of ECS
  -port <port_number>, -po <port_number>
                        port number of ECS
  -cf <cookiefile>, -cookiefile <cookiefile>
                        Full name of cookiefile
  -v, --version, -version
                        show version number of program and exit
```
# Stop and remove container
    # docker stop dellemc-ecscli
    # docker rm dellemc-ecscli
# Reference
CLI Installation and Configuration Guide https://www.emc.com/collateral/TechnicalDocument/docu86294.pdf
