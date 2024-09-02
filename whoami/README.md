# Whoami

## Quick start

1. Clone or download this repository.
1. Go inside of this directory `cd whoami`.
1. You can generate htpassword (whoami-auth) with the following command:
    ```
    docker run --rm -ti xmartlabs/htpasswd <username> <password> > htpasswd
    ```
1. Run command:
    - Podman:
        1. Start the "Podman systemD Socket", as Traefik requires it to handle containers:
            ```
            systemctl --user enable podman.socket
            systemctl --user start podman.socket
            ```
        1. Up/Down Whoami app:
            ```
            podman play kube whoami.yaml
            podman play kube --down whoami.yaml
            ```
        1. Up/Down Whoami Auth app:
            ```
            podman play kube whoami-auth.yaml
            podman play kube --down whoami-auth.yaml
            ```
        1. Podman commands:
            ```
            podman help
            podman ps
            (podman exec -it <ID> sh)
            (podman exec -it <ID> bash)
            podman pods ps
            podman pod stop <ID>
            podman pod start <ID>
            podman pod rm <ID>
            ```

## Access

Whoami:
- URL: `http://localhost:3000` or `http://whoami.localhost:8000` (Traefik)

Whoami Auth:
- URL: (`http://localhost:3001`) or `http://whoami-auth.localhost:8000` (Traefik)
- Basic authentication:
    - username: whoami
    - password: whoami

## Local DNS resolver

/etc/hosts

```
127.0.0.1 whoami.localhost whoami-auth.localhost
```
