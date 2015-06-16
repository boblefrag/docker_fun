# Build with :
# docker build -t qpid qpid/

# Run with :
# docker run -p 127.0.0.1:5672:5672 -t qpid /usr/sbin/qpidd --config /etc/qpid/qpidd.conf

FROM debian:latest
RUN echo deb http://ftp.de.debian.org/debian wheezy main >> /etc/apt/sources.list
RUN apt-get update
RUN echo qpidd qpidd/password1 password azerty | debconf-set-selections
RUN echo qpidd qpidd/password2 password azerty | debconf-set-selections

# we want the administrator password to be set because we are not able
# to enter it in the build step

RUN apt-get install qpidd qpid-tools libqpidmessaging2-dev python-qpid -y