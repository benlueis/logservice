FROM elasticsearch:latest

RUN apt-get update && apt-get install -y vim git

WORKDIR /opt
RUN wget https://nodejs.org/dist/v8.1.2/node-v8.1.2-linux-x64.tar.xz && tar -xvf node-v8.1.2-linux-x64.tar.xz
RUN mv node-v8.1.2-linux-x64 node
ENV PATH $PATH:/opt/node/bin

WORKDIR /usr/share/elasticsearch/plugins
RUN git clone https://github.com/mobz/elasticsearch-head.git \
    && cd elasticsearch-head \
    && npm install -g cnpm --registry=https://registry.npm.taobao.org \
    && npm install grunt --save

WORKDIR /usr/share/elasticsearch