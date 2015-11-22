alpine-skydns
================

skydns provides the service discovery through DNS

Usage
-----

To use this image include `FROM smebberson/alpine-consul` at the top of your `Dockerfile`, or simply `docker run --name consul --link "alpine-consul:consul-agent" smebberson/alpine-consul`.

It's very import to include a link to a container running a Consul agent (regardless if that Consul agent is running in server mode or not). The link within the container must be `consul-agent` which is used within `/etc/services.d/consul/run` to provide an IP that the Consul agent should join. Without this, the container will error and quit.

[s6]: http://www.skarnet.org/software/s6/
[consul]: https://www.consul.io/
[alpineconsul]: https://registry.hub.docker.com/u/smebberson/alpine-consul/
