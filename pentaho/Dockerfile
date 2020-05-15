FROM ubuntu:latest
COPY ./pentaho-server-ce-8.1.zip /pentaho/pentaho-server-ce-8.1.zip
RUN apt-get update && \ 
    apt-get install unzip && \ 
    apt-get install -y openjdk-8-jdk
RUN unzip /pentaho/pentaho-server-ce-8.1.zip -d /pentaho
#RUN rm /pentaho/pentaho-server/promptuser.sh
RUN rm /pentaho/pentaho-server/promptuser.sh
COPY ./promptuser.sh /pentaho/pentaho-server/promptuser.sh
RUN rm /pentaho/pentaho-server/start-pentaho.sh
COPY ./start-pentaho.sh /pentaho/pentaho-server/start-pentaho.sh
#RUN sh /pentaho/pentaho-server/start-pentaho.sh
RUN chmod +x /pentaho/pentaho-server/start-pentaho.sh
ENTRYPOINT /pentaho/pentaho-server/start-pentaho.sh
# ENTRYPOINT ["/bin/bash"]
