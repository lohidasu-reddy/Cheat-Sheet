# Knife Commands

```
## Getting Knife Version
knife --version
```

```
## Create Cookbook
knife cookbook create <cookbookName>

## Cookbook Download
knife cookbook download <cookbookName> <cookbookVer>

## List Cookbook on Chef Server
knife cookbook list

## Use Chef Supermarket
knife cookbook site list

```

```
## Getting List of all the client nodes
knife client list
```

```
## Bootstraping a Node
knife bootstrap <hostname/ipaddr> -x <username> -P <password> -N <nodeName>
```

```
## Server Bootstrap with Runlist
knife bootsrap <hostname> -x root -P <password> -N module3 -r "receipe[apache]"
```

```
## Server Bootstrap with Sudo with <user> providing user pem file as ssh identity with <nodename>, <runlist> and <environment> and additional <json_attribute> passing to the node

knife bootstrap <hostname> --sudo -x <user> -i <SSH Itentityfile> --node-name <nodename> \
--run-list <runlist> -E <Environment> \
--no-host-key-verify -j <json_attribute>
```

```
## Add Receipe to RunList for Node
knife node run_list add module2 "receipe[apache]"
```


```
## Knife Node Show

knife node show <nodename>
know node show <nodename> -a <keyName>
knife node show module2 -a apache
knife node show module2
```

```
## Knife Remove Item from run_list

knife node run_list remove module2 "receipe[apache]"
```

#### Knife Configure
Knife Configure command is used to create knife.rb and client.rb so that they can distribute to workstation and nodes.

```
## Configure client.rb
knife configure client <directory>

## Configure knife.rb
knife configure
```