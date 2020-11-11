# Nextcloud-ssl
Run nextcloud with **Docker MariaDB NGINX HTTPS Letsencrypt and Certbot** 


# Steps for Configuration. 
Clone the repository 
`git clone https://github.com/ehtishammubarik/nextcloud-ssl.git`
`cd nextcloud-ssl`
Open file docker-compose.yaml and add environment variable values for your database. Default values are
      - MYSQL_ROOT_PASSWORD=password
      - MYSQL_PASSWORD=password
      - MYSQL_DATABASE=nextcloud
      - MYSQL_USER=nextcloud

After setting up ENV run `docker-compose up -d` 
got to nginx directory. `cd data/nginx`
Open file app.conf (using any available editor) {e.g. `vim app.conf`} 
Replace every **example.org** with **YOUR_DOMAIN**
Now got to **test** directory pleaced in **nextcloud-ssl** 
Open **init-letsencrypt.sh** (using any available editor) {e.g. `vim init-letsencrypt.sh`}
Replace every **example.org** with **YOUR_DOMAIN** and give your **email**
Run this shell script with command `sudo bash init-letsencrypt.sh`
After successful execution of script make sure NGINX-APP-DB all three containers are up. 'docker ps' (to display running containers) 
Make sure that both HTTP and HTTPS ports are enabled on your server. 
Go to your browser and enter **YOUR_DOMAIN.COM**. 

                # CONGRATULATIONS!!
                    #You've configured nextcloud with docker and https redirection. 
