# XRDPGateway
A docker container which supports running remote X apps on a desktop accessible via RDP

This is a minor adaptation of an upstream docker image: https://hub.docker.com/r/rattydave/docker-ubuntu-xrdp-mate-custom/.
It adds SSH and Telnet clients, so that X clients could be run on other hosts. For full documentation,
please refer to the upstream container.

## Known issues

  * The upstream container hardcodes en_GB as the locale. This can create various problems, e.g. the characters ``"`` and ``@`` could be swapped.
