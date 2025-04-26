# Reverse Proxy Setup

My setup for exposing my home server to the internet without Port Forwarding.

## Tailscale

I use Tailscale to connect my home server with the docker in the VPS. This way I don't need to open ports in order to
connect this two endpoints.

## nginx

I use nginx to route my VPS traffic to the various services I have inside my home server.

## DNS Setup

First, I create an A record pointing to my server, this A record could be used for a specific service, but there I just
serve the default nginx page:

```
vps.gerardgascon.com.    IN    A    146.190.236.48
```

All subsequent domains I want to point to a home server service will have a CNAME pointing to that base A record:

```
git.gerardgascon.com.    IN    CNAME    vps.gerardgascon.com.
```