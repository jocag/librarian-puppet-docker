FROM centos:7
MAINTAINER "jocag@uma.es"

RUN yum -y update
RUN yum -y install ruby ruby-devel make sudo gcc git

RUN echo "gem: --no-ri --no-rdoc" > ~/.gemrc
RUN sudo sh -c 'echo "StrictHostKeyChecking no" >> /etc/ssh/ssh_config'

RUN gem install puppet -v 4.7.1
RUN gem install librarian-puppet -v 2.2.3
RUN gem install puppet-parse -v 0.1.4

# Set up the volumes and working directory
VOLUME ["/puppet"]
WORKDIR /puppet

ENTRYPOINT ["librarian-puppet"]
CMD ["install"]
