FROM jenkins/jenkins:2.275-jdk11

ARG DOCKER_VERSION="20.10.2"
ARG DOCKER_COMPOSE_VERSION="1.27.4"

USER root


RUN echo "" && \
    echo "Installing docker cli ${DOCKER_VERSION}" && \
        mkdir -p /tmp/docker && \
        curl --fail --silent --show-error --location https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz --output /tmp/docker/docker.tgz && \
        tar xzvf /tmp/docker/docker.tgz -C /tmp/docker && \
        cp /tmp/docker/docker/* /usr/local/bin && \
        rm -rf /tmp/docker && \
    echo "" && \
    echo "Installing docker-compose ${DOCKER_COMPOSE_VERSION}" && \
        curl --fail --silent --show-error --location https://github.com/docker/compose/releases/download/${DOCKER_COMPOSE_VERSION}/docker-compose-Linux-x86_64 --output /usr/local/bin/docker-compose && \
        chmod +x /usr/local/bin/docker-compose

USER jenkins
