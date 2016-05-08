FROM alpine

RUN apk --update add openjdk7-jre openssh git && \
    rm -rf /var/cache/apk/* 

RUN /usr/bin/java -version
RUN addgroup jenkins && \
    adduser -D jenkins -s /bin/sh -G jenkins && \
    chown -R jenkins:jenkins /home/jenkins && \
    echo "jenkins:jenkins" | chpasswd

RUN ssh-keygen -A

RUN set -x && \
    echo "UsePrivilegeSeparation no" >> /etc/ssh/sshd_config && \
    echo "PermitRootLogin no" >> /etc/ssh/sshd_config && \
    echo "AllowGroups jenkins" >> /etc/ssh/sshd_config

# Comment these lines to disable sudo
RUN apk --update add sudo && \
    rm -rf /var/cache/apk/* && \
    echo "%jenkins ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers

USER jenkins
EXPOSE 22
CMD ["sudo", "/usr/sbin/sshd", "-D"]
