FROM python:2.7

RUN curl -sL https://deb.nodesource.com/setup_4.x |  bash - \
    && apt-get install -y nodejs \
    && npm install -g bower

RUN git clone https://github.com/Kurento/kurento-tutorial-node.git \
    && cd kurento-tutorial-node/kurento-hello-world \
    && git checkout 6.9.0 \
    && npm install

CMD npm start