FROM openshift/jenkins-slave-base-centos7

RUN yum makecache && \
    yum install -y epel-release && \
    yum install -y python2-pip python-virtualenv gcc && \
    yum clean all -y

RUN virtualenv $HOME/venv && \
    . $HOME/venv/bin/activate && \
    pip install -U pip

ENV ENV $HOME/venv/bin/activate
ENV BASH_ENV $HOME/venv/bin/activate

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME
    
USER 1001
