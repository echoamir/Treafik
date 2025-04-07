```
labels:
      - "traefik.enable=true"
      - "traefik.docker.network=app_net"
      - "traefik.http.routers.website.entrypoints=http"
      - "traefik.http.routers.website.rule=Host(`amirkolahi.ir`)"
      - "traefik.http.routers.website.middlewares=https-redirect"
      - "traefik.http.middlewares.https-redirect.redirectscheme.scheme=https"
      - "traefik.http.routers.website-secure.entrypoints=https"
      - "traefik.http.routers.website-secure.rule=Host(`amirkolahi.ir`)"
      - "traefik.http.routers.website-secure.tls=true"
      - "traefik.http.routers.website-secure.tls.options=default"
      - "traefik.http.routers.website-secure.tls.certresolver=mycert"
      - "traefik.http.routers.website-secure.service=website"
      - "traefik.http.routers.website-secure.middlewares=hsts"
      - "traefik.http.middlewares.hsts.headers.stsSeconds=63072000"
      - "traefik.http.middlewares.hsts.headers.stsIncludeSubdomains=true"
      - "traefik.http.middlewares.hsts.headers.stsPreload=true"
      - "traefik.http.services.website.loadbalancer.server.port=80"

```
