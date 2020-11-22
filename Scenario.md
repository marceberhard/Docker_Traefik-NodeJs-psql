#Docker_Traefik_NodeJs_psql
See ReadMe





--------------------> Important things made in this project <--------------------

Compose-File:
- internal Networks for Microsegmentation
- Traefik Confgiruation
- port mappings
- environment definitions (Variables) ->  used variable defined in Dockerfile
-------------------------------------------------------------------------

Dockerfiles
- Variables used
- just made on 2 nodejs containers, other are prebuilt and standard-
-------------------------------------------------------------------------

GitLab CI/CD Pipeline
- I used 1 repo per NodeJs app --> no env-handling in GitLab used. ;)
- you must have a runner with docker support
- build images after every commit
- new images get built and pulled
- registered in your container registry
- you need to make sure to always pull latest image on server. see docker pull commands.
-------------------------------------------------------------------------

Traefik
- v2
- latest image
- used as a proxy
- Let'Encrypt certificate
- Port 80 reachability
- Port 443 reachability
- Port Forwarding 80->443, enforce TLS
- Service description -> NodeJs
- handled internal networks with loadbalancer -> in swiss words: "define where to find and use service" 
-------------------------------------------------------------------------

NodeJs frontend / backend tier
- no nodejs files not uploaded, insert your own.:)
- port 7777 exposed, listens container Service listen to them, make sure your app does as well or reconfigure yours.
- via port 9090 to backend NodeJs Server
- Service registration for Traefik, no auto discovery 
-------------------------------------------------------------------------

NodeJs backend / api tier
- no nodejs files not uploaded, insert your own.:)
- port 9090 exposed, listens container Service listen to them, make sure your app does as well or reconfigure yours.
- via port 5423 to DB Server
-------------------------------------------------------------------------

PostGres
- 13.1 image used
- in this scenarie no data stored in db
- make sure your db is fully persistent (docker)
- port 5432 exposed for reachability from backend NodeJs
