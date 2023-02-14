
## Guacamole

Install Guacamole with OpenMediaVault and Docker


## Prerequisites

- You’ll need a domain name.

- You’ll need to a CloudFlare account with your domain name pointed to it.

CloudFlare has a many resource on their website about, how to point your domain to their DNS servers.

## Installation

Open Portainer on your Server Machine and create a new Stack

Paste the following into your new stack:

```bash
version: "3"
services:
  guacamole:
    image: abesnier/guacamole
    container_name: guacamole
    volumes:
      - postgres:/config
    ports:
      - 8194:8080
volumes:
  postgres:
    driver: local
```

Click the “Deploy the Stack” button

## Go to your CloudFlare :
- Once you have the prerequisites  

- The next thing you're going to do is head over to CloudFlare's Zero Trust dashboard.(https://one.dash.cloudflare.com/)

- On the left, click "Access" and then "Tunnels".

- Then click the "Create a tunnel" button.

- Give your tunnel a name and click the save button.

- On the next page, click the "Docker" button. The screen will change and you'll see a Docker comman that you'll need to run

- Copy the docker run command and then log into your Docker server via the terminal.

- Once you're logged in, paste the command you just copied and let the docker container deploy.

- Give Some Time to do its thing, and after a moment, you should see that everything has been deployed correctly

- Once it's up and running, you should see that the "Connectors" portion of the "Install connector" page will update and show that things are connected 

- Next, go to 

## Route traffic to Guacamole Container:

- In Public hostname : Enter Sub-domain: http://guacamole.yourdomain.com

- Select yourdomain

- You'll select your service (http, https, ssh, rdp, etc) from the drop-down and then enter the ip address and port number of the Guacamole Application to access

- Service > Select "HTTP" 

- Enter the Server Machine IP Address followed by port number 8194 (Example: 192.168.1.61:8194)

- At this point, Give Sometime to finish all the process.

- Go to http://guacamole.yourdomain.com , you’ll be taken to the Guacamole dashboard!

## Default User:-

- The default username ```guacadmin``` with password ```guacadmin```
