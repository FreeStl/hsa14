## Architecture

           BIND CDN
         /        \
       NGINX1    NGINX2
     /     \     /     \
    app1   app2 app3   app4

Description:
- Bind DNS server
- Nginx nodes that cache responses from downstream services. Downstream services choosen with Round Robin algorithm. 
- simple Java service, that returns picture as responce to endpoint ; GET http://localhost:808x/api

# How to run
1) Enable local DNS resolution
2) Run docker compose file
3) send request to http://picture.com:81 and http://picture.com:82. Request will be redirected to nginx nodes

# Balancing:
- nginx config can be edited to try different balancing strategies