FROM debian:stable-slim

#RUN apt-get upgrade
RUN apt-get update

# needed for fahclient
RUN apt-get -y install wget bzip2
        
RUN wget https://download.foldingathome.org/releases/public/release/fahclient/debian-stable-64bit/v7.6/fahclient_7.6.8_amd64.deb
RUN mkdir -p /etc/fahclient/ 
RUN touch /etc/fahclient/config.xml

RUN dpkg -i --force-depends fahclient_7.6.8_amd64.deb
RUN rm -f fahclient_7.6.8_amd64.deb

WORKDIR /home/fah

RUN mkdir -p /home/fah/
RUN mkdir -p /home/fah/data
COPY ./entrypoint.sh /home/fah/entrypoint.sh

ENTRYPOINT [ "/home/fah/entrypoint.sh" ]
