# https://kamang-it.tistory.com/entry/DockerUbuntuSshd-%EC%9A%B0%EB%B6%84%ED%88%AC-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88-%EC%8B%A4%ED%96%89%ED%95%98%EA%B3%A0-%EC%9B%90%EA%B2%A9%EC%A0%91%EC%86%8D%ED%95%98%EA%B8%B0ssh

FROM ubuntu:20.10

MAINTAINER parangee <parangee9706@gmail.com>

RUN apt update

RUN apt install -y openssh-server

RUN mkdir /var/run/sshd

RUN echo 'root:password' | chpasswd

RUN sed -ri 's/^#?PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config

RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

RUN mkdir /root/.ssh

RUN apt clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
