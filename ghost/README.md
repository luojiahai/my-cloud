# Ghost

**Ghost** is an open source headless Node.js CMS, a blogging platform. The web application will be containerised by Docker, be composed by `docker-compose` associating with other essential services (database, web server and SSL) and be ready to serve on an IaaS cloud machine.

## Logistics

1. Create a VM with image Ubuntu 16.04/18.04/20.04.

2. Add inbound ports 80 (HTTP) and 443 (HTTPS) in the security groups.

## Install Docker and ```docker-compose```

Login to the VM and follow steps A, B and C in [here](https://luojiahai.net/install-docker-engine-on-ubuntu/).

## Install Ghost

1. Set enviornment variables. 
   1. Create a file called `.env` in the same directory as `docker-compose.yml`.
   2. Copy all the content in `example.env` and paste into `.env`.
   3. Change the values accordingly.
   4. Save.

2. Run the following Docker Compose command:
   ```
   $ docker-compose up -d
   ```
   
3. Wait at least a minute for the web application to initialise after it has been successfully composed.

## Setup Ghost

1. Enter https://{HOST}/ghost in your preferred browser.

2. Follow the instruction to initialise your website.

3. Done! 

4. Browse the existing posts for tutorial.
