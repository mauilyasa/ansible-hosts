FROM fedora:34

RUN dnf update -y && \
    dnf install -y openssh-server sudo && \
    dnf clean all && \
    mkdir /var/run/sshd && \
    # Set root password
    echo 'root:root' | chpasswd && \
    sed -i 's/#PermitRootLogin yes/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config && \
    sed -i 's/#PubkeyAuthentication yes/PubkeyAuthentication yes/' /etc/ssh/sshd_config

RUN mkdir -p /root/.ssh && \
    chmod 700 /root/.ssh

# Optional  to authorized_keys
#COPY PATH/TO/key.pub /root/.ssh/authorized_keys
#RUN chmod 600 /root/.ssh/authorized_keys && \
#    chown root:root /root/.ssh/authorized_keys

CMD ["/usr/sbin/sshd", "-D"]
