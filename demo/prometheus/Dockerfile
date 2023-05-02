FROM ubuntu:22.04
WORKDIR /
RUN apt-get update && apt-get install -y wget git && wget --quiet https://github.com/prometheus/prometheus/releases/download/v2.42.0/prometheus-2.42.0.linux-amd64.tar.gz && tar xvfz prometheus-2.42.0.linux-amd64.tar.gz && mv prometheus-2.42.0.linux-amd64 prometheus
ADD https://api.github.com/repos/zachs18/zerotrust/git/refs/heads/demo-v1 version.json
RUN git clone --depth 1 --branch demo-v1 https://github.com/zachs18/zerotrust.git
WORKDIR /zerotrust/demo/prometheus
ENTRYPOINT ["/prometheus/prometheus", "--config.file=./prometheus.yaml"]
