FROM debian

LABEL maintainer="YaQwaQwa <lnzimand@student.wethinkcode.co.za>"

ENV TSV=3.5.5 TS3SERVER_LICENSE=accept
#Accepts the teamspeak license

WORKDIR /home/teamspeak

EXPOSE 9987/udp 10011 30033

RUN apt-get update && apt-get upgrade -y && apt-get install -y wget bzip2 && \
	wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2  && \
	tar xvf *.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh

# Building it
# docker build -t ex01:1.0 .

# How to run it?
# docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01:1.0
	
#Resources: 
# https://docs.docker.com/samples/library/teamspeak/#container-shell-access
# https://www.vultr.com/docs/how-to-install-teamspeak-3-server-on-ubuntu-16-04-64-bit
