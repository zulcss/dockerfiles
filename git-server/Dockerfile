from ubuntu:xenial

run apt update && apt dist-upgrade -y \
	&& apt install -y openssh-server git
run mkdir /var/run/sshd
run ssh-keygen -A

workdir /git-server/
run mkdir /git-server/keys \
 && adduser --shell /bin/git-shell git \
	&& echo git:12345 | chpasswd \
	&& mkdir /home/git/.ssh

copy start.sh start.sh
COPY git-shell-commands /home/git/git-shell-commands

expose 22

cmd ["sh", "start.sh"]
