FROM ubuntu:20.04

RUN apt update
RUN apt install -y gcc python-dev unzip wget vim python3-pip ansible
RUN wget https://releases.hashicorp.com/terraform/0.15.4/terraform_0.15.4_linux_amd64.zip
RUN unzip terraform_0.15.4_linux_amd64.zip
RUN mv terraform /usr/local/bin/
RUN wget https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip
RUN unzip awscli-exe-linux-x86_64.zip
RUN ./aws/install
RUN pip3 install --upgrade pip
RUN pip3 install --upgrade virtualenv
RUN pip3 install requests



RUN adduser --disabled-password --gecos 'Aaron' aaron \
 && adduser aaron sudo
COPY sudoers /etc/sudoers
USER aaron
RUN mkdir ~/.aws && touch ~/.aws/credentials
WORKDIR /home/aaron

VOLUME /home
CMD ["/bin/bash"]

