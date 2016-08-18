#
# (c) 2016, PJ$
# me@pjstein.co
# dock
#
# dock/phantom/Dockerfile
#

# Just a rip off of the stuff here: 
# https://github.com/fatihcode/dockerhub/blob/master/phantomjs/Dockerfile
# I wanted to get a feel for the syntax and such

FROM       node
MAINTAINER pjstein

ENV VERSION 2.1.1

RUN apt-get update     && \
    apt-get upgrade -y && \
    apt-get install -y    \
      wget                \
      libfreetype6        \
      libfontconfig       \
      bzip2            && \
    wget -q --no-check-certificate -O /tmp/phantomjs-${VERSION}-linux-x86_64.tar.bz2 \
      https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-${VERSION}-linux-x86_64.tar.bz2 && \
    tar -xjf  /tmp/phantomjs-${VERSION}-linux-x86_64.tar.bz2 -C /tmp && \
    rm    -f  /tmp/phantomjs-${VERSION}-linux-x86_64.tar.bz2         && \
    mkdir -p  /opt/lib/  && \
    mv        /tmp/phantomjs-${VERSION}-linux-x86_64 /opt/lib/ && \
    ln    -s  /opt/lib/phantomjs-${VERSION}-linux-x86_64/bin/phantomjs /usr/bin/phantomjs && \
    apt-get   autoremove -y && \
    apt-get   clean all

CMD [ "/usr/bin/phantomjs" ]
