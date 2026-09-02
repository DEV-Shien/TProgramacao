FROM jenkins/jenkins:lts
USER root

# Instalar NodeJS (o npm já vem incluído)
RUN curl -fsSL https://deb.nodesource.com/setup_20.x | bash -
RUN apt-get update
RUN apt-get install -y nodejs
RUN apt-get clean

# Garantir que o workspace do Jenkins tenha permissões corretas
RUN mkdir -p /var/jenkins_home/workspace && chown -R jenkins:jenkins /var/jenkins_home

USER jenkins