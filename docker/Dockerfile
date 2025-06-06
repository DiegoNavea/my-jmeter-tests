FROM alpine:latest

RUN apk add --no-cache openjdk17 curl unzip bash

# Download and install JMeter
RUN curl -L -o /tmp/jmeter.tgz https://dlcdn.apache.org/jmeter/binaries/apache-jmeter-5.6.3.tgz && \
    mkdir /opt && tar -xzf /tmp/jmeter.tgz -C /opt && \
    ln -s /opt/apache-jmeter-5.6.3 /opt/jmeter

ENV JMETER_HOME=/opt/jmeter
ENV PATH=$JMETER_HOME/bin:$PATH

WORKDIR /tests

ENTRYPOINT ["jmeter"]
