
## Context
The intention of the guide is to : 
- 
 
## References


## Requirements

-   Hardware
	- **64bit linux distribution** 
		- running in virtual machine (VM) or dedicated server 
		- within a simple virtual machine on desktop if required. 
	-   two CPU / 3GB Memory / 32 GB Storages
-   Software:
	- Docker
	-  Domain Name System (DNS) Server if possible
		- This will allow local domains such as mail.local
	-  Web Browser
- All devices on the same local network


## Instructions
### Setup
#### Full Scripts
```BASH

```


#### By The Numbers
```BASH
#Install Docker
sudo apt update; sudo apt install -y docker docker.io
```

```BASH
#run docker command after modifying domain
docker run \
    --net=host \
    -e TZ=America/New_York \
    -v /var/mailserver:/data \
    --name "mailserver" \
    -h "mail.example.local" \
    -t analogic/poste.io
```

After that, you can open a Web browser to the domain of the VM or device running this email server. 

Close Terminal window and confirm mail server is still working on browser. 
### Administration
#### Local Email Administration Management
#### Command line

for docker supporting **exec** command:

```
# docker exec <container-id> poste

Mailserver commandline API version 1.0

Usage:
command [options] [arguments]

Options:
-h, --help            Display this help message
-q, --quiet           Do not output any message
-V, --version         Display this application version
--ansi            Force ANSI output
--no-ansi         Disable ANSI output
-n, --no-interaction  Do not ask any interactive question
-v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output, 2 for more verbose output, and 3 for debug

Available commands:
help            Displays help for a command
list            Lists commands
domain
domain:create   Create virtual domain
domain:dkim     Show/create/remove DKIM keys&selector
domain:list     Show all domains
domain:remove   Delete virtual domain with all mailboxes and data
domain:warm-up  (Internal command!) Force recreate delivery domain configs
email
email:admin     Set/Unset email super admin rights
email:create    Create mailbox skeleton
email:list      Show all mailboxes
email:passwd    Change password for mailbox
email:quota     Show/set quota for mailbox
email:remove    Delete mailbox
email:sieve     Set sieve script (from pipe) or show current script
        
```

or you can control mailserver from inside container

```
# poste help domain:create

Usage:
domain:create [options] [--] <domain>

    Arguments:
    domain                domain name

    Options:
    --json            ouput JSON only
    -h, --help            Display this help message
    -q, --quiet           Do not output any message
    -V, --version         Display this application version
    --ansi            Force ANSI output
    --no-ansi         Disable ANSI output
    -n, --no-interaction  Do not ask any interactive question
    -v|vv|vvv, --verbose  Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

    Help:
    Create virtual domain
        
```

example:

```
# poste domain:create newdomain.com

Successfully created virtual domain newdomain.com


# poste email:create test@newdomain.com mySecretPassword1

Successfully created email box test@newdomain.com with mySecretPassword1
```
