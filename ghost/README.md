# Ghost

**Ghost** is an open source headless Node.js CMS, a blogging platform. The web application will be containerised by Docker, be composed by `docker-compose` associating with other essential services (database, web server and SSL) and be ready to serve on an IaaS cloud machine.

**Please allocate at least 1GB RAM on your cloud machine.**

## Logistics

1. In your domain service provider, set DNS type A record pointing to the public IP of your cloud machine for your chosen domain.

2. In your cloud service provider, add inbound ports 80 (HTTP) and 443 (HTTPS) to the security group of your cloud machine.

## Install Docker Engine - Community (on Ubuntu)

1. Update the `apt` package index:
   ```
   $ sudo apt-get update
   ```

2. Install packages to allow `apt` to use a repository over HTTPS:
   ```
   $ sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
   ```
   
3. Add Docker’s official GPG key:
   ```
   $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   ```
   Verify that you now have the key with the fingerprint `9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88`, by searching for the last 8 characters of the fingerprint.
   ```
   $ sudo apt-key fingerprint 0EBFCD88
   
   pub   rsa4096 2017-02-22 [SCEA]
         9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
   uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
   sub   rsa4096 2017-02-22 [S]
   ```
   
4. Use the following command to set up the stable repository. To add the nightly or test repository, add the word nightly or test (or both) after the word stable in the commands below.
   ```
   $ sudo add-apt-repository \
     "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
     $(lsb_release -cs) \
     stable"
   ```
   
5. Update the `apt` package index.
   ```
   $ sudo apt-get update
   ```
   
6. Install the latest version of Docker Engine - Community and containerd, or go to the next step to install a specific version:
   ```
   $ sudo apt-get install docker-ce docker-ce-cli containerd.io
   ```
   
7. Verify that Docker Engine - Community is installed correctly by running the `hello-world` image.
   ```
   $ sudo docker run hello-world
   ```
   
8. Add your user to the "docker" group to use Docker as a non-root user.
   ```
   $ sudo usermod -aG docker your-user
   ```

## Install Docker Compose (on Linux systems)

1. Run this command to download the current stable release of Docker Compose:
   ```
   $ sudo curl -L "https://github.com/docker/compose/releases/download/1.25.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   ```
   
2. Apply executable permissions to the binary:
   ```
   $ sudo chmod +x /usr/local/bin/docker-compose
   ```
   
   Note: If the command `docker-compose` fails after installation, check your path. You can also create a symbolic link to `/usr/bin` or any other directory in your path.
      ```
      $ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
      ```
 
3. Test the installation.
   ```
   $ docker-compose --version
   ```

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
