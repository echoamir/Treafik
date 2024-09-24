```
- traefik.enable=true
- traefik.docker.network=web_app
- traefik.http.routers.wp.middlewares=https-redirect
- traefik.http.middlewares.https-redirect.redirectscheme.scheme=https
- traefik.http.routers.wp.entrypoints=http
- traefik.http.routers.wp.rule=Host(``)
- traefik.http.routers.wp-secure.entrypoints=https
- traefik.http.routers.wp-secure.rule=Host(``)
- traefik.http.routers.wp-secure.tls=true
- traefik.http.routers.wp-secure.tls.options=default
- traefik.http.routers.wp-secure.tls.certresolver=mycert
- traefik.http.routers.wp-secure.service=wordpress
- traefik.http.services.wordpress.loadbalancer.server.port=80
```
