# Traefik

## Quick start

1. Clone or download this repository.
1. Go inside of this directory `cd traefik`.
1. Run command:
    - Podman:
        1. Start the "Podman systemD Socket", as Traefik requires it to handle containers:
            ```
            systemctl --user enable podman.socket
            systemctl --user start podman.socket
            ```
        1. Up/Down Traefik app:
            ```
            podman play kube traefik.yaml
            podman play kube --down traefik.yaml
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

Traefik:
- URL: (`http://localhost:8001`) or `http://traefik.localhost:8000` (Traefik)
- Basic authentication:
    - username: traefik
    - password: traefik

## Local DNS resolver

/etc/hosts

```
127.0.0.1 traefik.localhost
```
