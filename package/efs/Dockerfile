FROM ubuntu:16.04
RUN apt-get update && \
    apt-get install -y jq python2.7 curl nfs-common dnsutils
RUN curl https://bootstrap.pypa.io/pip/2.7/get-pip.py --output get-pip.py
RUN python2.7 get-pip.py
RUN pip install awscli
COPY storage /usr/bin/
COPY efs/rancher-efs common/* /usr/bin/
CMD ["start.sh", "storage", "--driver-name", "rancher-efs"]
