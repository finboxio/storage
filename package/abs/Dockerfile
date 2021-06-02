FROM ubuntu:16.04
RUN apt-get update && \
    apt-get install -y jq python2.7 curl
RUN curl https://bootstrap.pypa.io/pip/2.7/get-pip.py --output get-pip.py
RUN python2.7 get-pip.py
RUN pip install aliyun-python-sdk-ecs && \
    pip install aliyuncli
COPY storage /usr/bin/
COPY abs/rancher-abs common/* /usr/bin/
RUN chmod a+x /usr/bin/rancher-abs
CMD ["start.sh", "storage", "--driver-name", "rancher-abs"]
