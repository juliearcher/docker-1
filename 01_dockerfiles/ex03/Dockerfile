FROM ubuntu

WORKDIR /
RUN apt-get update -y && apt-get upgrade -y && apt-get install wget ca-certificates openssh-server curl postfix -y
RUN wget https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh
RUN bash script.deb.sh
RUN apt-get install gitlab-ce -y
RUN apt-get update -y && apt-get upgrade -y && apt-get install tzdata -y && apt-get clean

EXPOSE 22 80 443
ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && tail -f /dev/null

# docker build -t imagegitlab .
# docker run --rm -it -p8080:80 -p8022:22 -p8443:443 --privileged imagegitlab
