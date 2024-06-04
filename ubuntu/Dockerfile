FROM ubuntu:20.04

RUN apt-get update && \
    apt-get install -y openssh-server sudo && \
    apt-get clean && \
    mkdir /var/run/sshd && \
    echo 'root:root' | chpasswd && \
    sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config && \
    mkdir -p /root/.ssh && \
    chmod 700 /root/.ssh

# If you have key uncomment this

#COPY key.pub /root/.ssh/authorized_keys
#RUN chmod 600 /root/.ssh/authorized_keys && \
#    chown root:root /root/.ssh/authorized_keys

CMD ["/usr/sbin/sshd", "-D"]
