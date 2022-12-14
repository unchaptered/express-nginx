[< λ€λ‘κ°κΈ°](./README.md)

### π Nginx

```cmd
sudo -s
sudo apt-get update
sudo apt-get install nginx <!-- nginx.install.md -->
sudo service ngnix start <!-- nginx.start.md -->
```

![](./Nginx%20Page.png)

<hr>

### π Install node

```cmd
curl -s https://deb.nodesource.com/setup_16.x | sudo bash
sudo apt-get install -y nodejs
```

![](./Node%20Install%20Result.png)

<hr>

### π Install pm2

```cmd
sudo npm install -g pm2
```

![](./Node%20Install%20PM2%20Result.png)

<hr>

### π npm global list

```cmd
npm ls -g
```

![](./Node%20Install%20PM2%20List%20Result.png)\

### π Nginx Reverse Proxy μ€μ  ν μ¬λΆν

```cmd
cd /etc/nginx/sites-enabled

ls
sudo rm default
sudo nano default
```

νμ λ€μ νμΌ λ³΅μ¬ λΆμ¬ λ£κΈ° ν `Ctrl + S`, `Ctrl + X`.

```default
server {
        listen 80;
        listen [::]:80;

        access_log /var/log/nginx/reverse-access.log;
        error_log /var/log/nginx/reverse-error.log;

        location / {
                    proxy_pass http://127.0.0.1:3000;
  }
}
```

νμ λ€μ λͺλ Ήμ΄λ‘ μ λλ‘ μ€μ  λμλμ§ νμΈν  μ μμ΅λλ€.

```cmd
sudo nginx -t
```

![](./Nginx%20Configuration%20Check.png)

νμ λ€μ λͺλ Ήμ΄λ‘ nginx μ μ¬μμ ν  μμ΅λλ€.

```cmd
sudo service nginx restart
```