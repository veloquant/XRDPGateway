# XRDPGateway
A docker container which supports running remote X apps on a desktop accessible via RDP

This is a minor adaptation of an upstream docker image: https://hub.docker.com/r/rattydave/docker-ubuntu-xrdp-mate-custom/.
It adds SSH and Telnet clients, so that X clients could be run on other hosts. For full documentation,
please refer to the upstream container.

Below is an example invocation on a Linux or Mac host. Please use your home-directories base directory and set-up createusers.txt as explained in the documentation of the base image referenced above. Also, see it for a Windows example.

    docker run --name XRDPGateway --privileged=true -p 3389:3389 -v ${PWD}/createusers.txt:/root/createusers.txt -v /home:/home -dit --restart unless-stopped yitzikc/xrdpgateway:19.04


## Known issues

  * The upstream container hardcodes en_GB as the locale. This can create various problems, e.g. the characters ``"`` and ``@`` could be swapped.
