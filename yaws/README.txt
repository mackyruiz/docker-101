Yet Another Web Server (yaws)

This is my first docker file that does several things:
 1. updates /usr/local/apache2/conf to use port 8080 and 443
 2. Use the self-signed certificates for SSL
 3. Run apache in the foreground


To build, run this in the directory:
  docker build --rm -t my_httpd .

To spin off a container based on the image that was created:
  docker run -d --name=webserver -p8080:8080 -p443:443 myhttpd

You should be able to open a web browser and verify that its running on both :8080 and :443:
http://localhost:8080
https://localhost

You should be greated with the default "It Works!" index page
