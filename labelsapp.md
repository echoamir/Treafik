```

    labels:
      - traefik.enable=true
      - traefik.docker.network=web_app
      - traefik.http.routers.APPNAME.entrypoints=http
      - traefik.http.routers.APPNAME.rule=Host(``)
      - traefik.http.routers.APPNAME.service=APPNAME-secure
      - traefik.http.routers.APPNAME.middlewares=https-redirect
      - traefik.http.routers.APPNAME-secure.entrypoints=https
      - traefik.http.routers.APPNAME-secure.rule=Host(``)
      - traefik.http.routers.APPNAME-secure.service=APPNAME-secure
      - traefik.http.routers.APPNAME-secure.tls.certresolver=mycert
      - traefik.http.routers.APPNAME.entrypoints=http
      - traefik.http.routers.APPNAME-secure.entrypoints=https
      - traefik.http.routers.APPNAME-secure.tls=true
      - traefik.http.routers.APPNAME-secure.tls.options=default
      - traefik.http.routers.APPNAME-secure.tls.certresolver=mycert
      - traefik.http.services.APPNAME-secure.loadbalancer.server.port=80
```
