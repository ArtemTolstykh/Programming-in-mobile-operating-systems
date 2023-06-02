1)
docker pull nginx
docker run -p 80:80 -v /home/user/nginx:/usr/share/nginx/html nginx
открыть http://localhost

2)
docker pull httpd
docker run -p 80:80 -v /home/user/apache:/usr/local/apache2/htdocs/ httpd
открыть http://localhost
