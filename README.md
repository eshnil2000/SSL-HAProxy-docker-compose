# SSL with HAProxy in docker container - docker-compose.yml
Adapted from:
https://blog.georgejose.com/moving-my-http-website-to-https-using-letsencrypt-haproxy-and-docker-deb56ff6be9b

#### Add a folder under folder haproxy called "private"
```
mkdir haproxy/private
```

#### Copy your SSL certificates here
If you used Letsencrypt:
```
cat /etc/letsencrypt/live/yourdomain.com/fullchain.pem /etc/letsencrypt/live/yourdomain.com/privkey.pem > haproxy/private/yourdomain.com.pem
```

#### /etc/letsencrypt/live/yourdomain.com/ contents:
cert.pem       chain.pem      fullchain.pem  privkey.pem    README
You might need to copy the pem files into pem folder and then run the cat command

#### install node packages
```
cd personal-website
npm install
```


#### Run 
```
docker-compose up
```

#### Browse to your domain

#### Pre-requisites:
1. Ensure server ports 443, 80 are open
2. Ensure docker is installed

