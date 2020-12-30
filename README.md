# Docker-PHP-MYSQL
PHP &amp; MySql application to connect between three images (php-mysql-phpmyadmin) with docker-compose.
<!--<html>
<head>
<style>
code {
  font-family: Consolas,"courier new";
  color: crimson;
  background-color: #f1f1f1;
  padding: 2px;
  font-size: 105%;
}
</style>
</head>
<body>-->
# OS
Ubuntu
# Images
1-MYSQL 2-PHP 3-phpMyAdmin
# Step to run services
<h3>1-install docker-compose</h3>
<p><code>sudo apt install docker-compose</code></p>
<h3>2-build the image with docker commande</h3>
<p><code>sudo docker build . -t anyname/moe-php-mysql-demo:1.0.0</code></p>
<h3>3-run the image with the below command</h3>
<p><code>$ sudo docker run -d -it -p 30001:80 --name "moe-php-mysql-app" \
-v "$(pwd)"/www:/var/www/html \
anyname/moe-php-mysql-demo:1.0.0</code></p>
 You can replace port 30001 with any number. 
 The -p 30001:80 is telling that to publish the port 80 to host's 30001 port. Now you can access your application to http://localhost:30001 in any web browser.
 Also the -v "$(pwd)"/www:/var/www/html option is telling to bind a volume to the container's /var/www/html directory to "$(pwd)"/www. This will help the
 development as every time you do a code change it will be reflected ASAP to the container application

<h3>4-Now deploy the all three images with docke-compose.yml</h3>
<p><code>$ sudo docker-compose up --build</code></p>

<h3>5-Now check the application is available at http://localhost:30001</h3>

![index](https://user-images.githubusercontent.com/45989263/103385777-7a600e80-4b04-11eb-9cb4-2cde05fabf57.png) 

<h3>6-go to phpmyadmin with http://localhost:30002 </h3>
<p><code>import file CEM_ITEM_T.sql from folder db_scrips</code></p>

![phpmyadmin](https://user-images.githubusercontent.com/45989263/103385803-9b286400-4b04-11eb-9e82-e96f61085e4e.png) 


<h3>7-Access this page by http://localhost:30001/mysql-connect.php</h3>

![home](https://user-images.githubusercontent.com/45989263/103385793-8c41b180-4b04-11eb-963d-37cad141eb2b.png) 


<h3>8- check conect mysql with php and show table</h3>
<p><click on check conect with mysql></p>
  
![db](https://user-images.githubusercontent.com/45989263/103385841-bf844080-4b04-11eb-8ddc-4b82e86d10fb.png)





</body>
</html>
