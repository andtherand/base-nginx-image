# docker-base-nginx
a base nginx-image to extend

A docker image that installs the latest nginx webserver.
To be able to use it you have to extend it with another image.


For example:
The following folder structure is assumed:

```
ROOT of image
|
+-+ 
   \ 
    files
      +
      |
      +-+
      |  \ 
      |   vhost.conf
      |
      +-+
         \ 
          start.sh
```


```
FROM mychiara/nginx
MAINTAINER Andy Ruck

ADD /files/vhost.conf /etc/nginx/sites-enabled/vhost.conf

ADD /files/start.sh /etc/service/nginx/run
RUN chmod +x /etc/service/nginx/run # actual start of the container
```
