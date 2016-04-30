FROM mhart/alpine-node:4

RUN apk --update add openjdk7-jre openssh

RUN /usr/bin/java -version
RUN addgroup jenkins && \
    adduser -D jenkins -s /bin/sh -G jenkins && \
    chown -R jenkins:jenkins /home/jenkins
RUN echo "jenkins:jenkins" | chpasswd

RUN ssh-keygen -A
RUN echo "/usr/sbin/sshd -D" | tee -a /start.sh
RUN chmod +x ./start.sh

EXPOSE 22

RUN sed -i "s/UsePrivilegeSeparation.*/UsePrivilegeSeparation no/g" /etc/ssh/sshd_config \
	&& sed -i "s/UsePAM.*/UsePAM no/g" /etc/ssh/sshd_config \
	&& sed -i "s/#PermitRootLogin.*/PermitRootLogin yes/g" /etc/ssh/sshd_config

RUN apk --update add git

RUN echo "AllowGroups jenkins|tee -a /etc/sshd_config"

CMD ["/bin/sh", "./start.sh"]
