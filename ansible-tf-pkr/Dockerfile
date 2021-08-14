FROM ubuntu:latest
RUN apt-get update \
    && apt install -y apt-transport-https gnupg ca-certificates zip unzip git python3 python3-pip curl 

RUN curl https://releases.hashicorp.com/terraform/1.0.4/terraform_1.0.4_linux_amd64.zip -o /tmp/terraform.zip \
    && unzip /tmp/terraform.zip -d /usr/local/bin \
    && rm -rf /tmp/terraform.zip \
    && terraform --version

RUN curl https://releases.hashicorp.com/packer/1.7.4/packer_1.7.4_linux_amd64.zip -o /tmp/packer.zip \
    && unzip /tmp/packer.zip -d /usr/local/bin \
    && rm -rf /tmp/packer.zip \
    && packer --version


RUN curl https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip -o /tmp/awscliv2.zip \
    && unzip /tmp/awscliv2.zip -d /opt \
    && /opt/aws/install -i /usr/local/aws-cli -b /usr/local/bin \
    && rm /tmp/awscliv2.zip \
    && rm -rf /opt/aws \
    && aws --version

RUN pip3 install ansible

CMD ["/bin/bash"]

