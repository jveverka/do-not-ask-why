FROM maven:3.6.3-amazoncorretto-11
RUN yum -y install man vi vim git wget curl unzip telnet nmap iputils bind-utils postgresql
RUN wget https://releases.hashicorp.com/terraform/0.14.5/terraform_0.14.5_linux_amd64.zip && unzip terraform_0.14.5_linux_amd64.zip && chmod 755 terraform && mv terraform /bin/ && rm -f terraform_0.14.5_linux_amd64.zip
RUN wget https://storage.googleapis.com/kubernetes-release/release/v1.20.4/bin/linux/amd64/kubectl && chmod +x ./kubectl && mv kubectl /bin/
RUN wget https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip && unzip awscli-exe-linux-x86_64.zip && ln -s /aws/dist/aws /bin/aws
COPY README-docker.md /README.md
COPY loop.sh /loop.sh
ENTRYPOINT ["/loop.sh"]
