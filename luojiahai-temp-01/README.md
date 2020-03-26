# Ghost

## Install Docker Engine - Community

### 
1. Update the ```apt``` package index:
   ```
   $ sudo apt-get update
   ```

2. Install packages to allow ```apt``` to use a repository over HTTPS:
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
   Verify that you now have the key with the fingerprint ```9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88```, by searching for the last 8 characters of the fingerprint.
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
   
5. Update the apt package index.
   ```
   $ sudo apt-get update
   ```
   
6. Install the latest version of Docker Engine - Community and containerd, or go to the next step to install a specific version:
   ```
   $ sudo apt-get install docker-ce docker-ce-cli containerd.io
   ```
   
7. Verify that Docker Engine - Community is installed correctly by running the hello-world image.
   ```
   $ sudo docker run hello-world
   ```
