FROM debian:stable
RUN apt update && apt upgrade -y && apt dist-upgrade -y
RUN apt install tor -y
EXPOSE 9050
USER tor
CMD tor --socksport 0.0.0.0:9050
