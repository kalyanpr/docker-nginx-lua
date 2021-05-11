# docker-nginx-lua
nginx-lua
Create your own Dockerfile ...

COPY /your/nginx.conf /nginx/conf/nginx.conf
Add this location block to your nginx.conf file

location /hellolua {
    content_by_lua '
        ngx.header["Content-Type"] = "text/plain";
        ngx.say("hello world");
    ';
}
If you don't have an nginx.conf file then use the conf file provided in the github repo

The conf file provided is the default generated conf file with the above location block added

Build your docker image

Run your docker container - Remember to use -p YOUR_PORT:80 in your docker run statement
