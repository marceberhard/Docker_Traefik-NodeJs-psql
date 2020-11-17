#Docker_Traefik_NodeJs_psql
**** ------------------------------------------------------------------------- ****
  Excercise and contents:
  -----Build docker images using GitLab CI / CD Pipelines. 
  -----Traefik v2 Proxy -> WebApp on 2 NodeJs with Port Forwarding. psql as db.
**** ------------------------------------------------------------------------- ****


Traefik
- v2
- latest image
- used as a proxy
- Let'Encrypt certificate
- Port 80 reachability
- Port 443 reachability
- Port Forwarding 80->443, enforce TLS
- Service description -> NodeJs
-------------------------------------------------------------------------

NodeJs frontend / backend tier
- no nodejs files not uploaded, insert your own.:)
- port 7777 exposed, listens container Service listen to them, make sure your app does as well or reconfigure yours.
- via port 9090 to backend NodeJs Server
- Service registration for Traefik, no auto discovery 
-------------------------------------------------------------------------

NodeJs backend / api tier
- no nodejs files not uploaded, insert your own.:)
- port 7777 exposed, listens container Service listen to them, make sure your app does as well or reconfigure yours.
- via port 9090 to backend NodeJs Server
- Service registration for Traefik, no auto discovery 
-------------------------------------------------------------------------

PostGres
- latest image used
- in this scenarie no data stored in db
- make sure your db is fully persistent (docker)
- port 5432 exposed for reachability from backend NodeJs
