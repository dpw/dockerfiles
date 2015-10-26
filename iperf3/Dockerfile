FROM ubuntu:trusty

RUN apt-get update && apt-get install -y build-essential curl \
    && cd /tmp \
    && curl -L https://github.com/esnet/iperf/archive/3.1.tar.gz | tar xzf - \
    && cd iperf-3.1 \
    && ./configure --prefix=/usr \
    && make install \
    && cd .. \
    && rm -rf iperf-3.1 \
    && apt-get purge -y build-essential curl

EXPOSE 5201
ENTRYPOINT ["/usr/bin/iperf3"]
CMD ["-s"]
