FROM debian:buster

RUN apt-get clean && apt-get update \
&& apt-get install -y ansible

ADD files /tmp/files

RUN ansible-galaxy install ansible-thoteam.nexus3-oss \
&& ansible-galaxy install geerlingguy.java \
&& ansible-playbook /tmp/files/nexus.yaml

ENTRYPOINT service nexus start