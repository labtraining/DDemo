FROM jenkins:latest
MAINTAINER RajaPandian <pandian_3k@hotmail.com>

USER root

RUN \
    apt-get update && \
    apt-get install -y build-essential && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

COPY docker /usr/bin/docker

# To allow us to access /var/run/docker.sock on the Mac
RUN gpasswd -a jenkins staff

USER jenkins

ENTRYPOINT ["/bin/tini", "--", "/usr/local/bin/jenkins.sh"]