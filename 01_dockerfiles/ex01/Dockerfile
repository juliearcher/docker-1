FROM debian

ENV	TS3SERVER_LICENSE=accept
WORKDIR /home/ts
EXPOSE 9987/udp 10011 30033

RUN apt-get update -y && apt-get upgrade -y && apt-get install wget -y && apt-get install bzip2 -y
RUN	wget http://dl.4players.de/ts/releases/3.8.0/teamspeak3-server_linux_amd64-3.8.0.tar.bz2
RUN	tar -xvf teamspeak3-server_linux_amd64-3.8.0.tar.bz2
RUN	rm teamspeak3-server_linux_amd64-3.8.0.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT sh ts3server_minimal_runscript.sh start
# docker build -t imagets .
# docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 imagets
