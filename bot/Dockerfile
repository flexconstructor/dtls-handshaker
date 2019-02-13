FROM python:2.7

RUN curl -sL https://deb.nodesource.com/setup_4.x |  bash - \
    && apt-get install -y nodejs \
                          libnice-dev \
                          npm \
    && npm install -g n \
    && n 0.10 \
    && npm explore npm -g -- npm install -g node-gyp
COPY rootfs /

ENV PATH=$PATH:/opt/node/lib/node_modules/node-gyp/bin/
WORKDIR /client
RUN ls -la
RUN npm install
RUN cp /tools/libnice/binding.gyp node_modules/libnice
RUN node-gyp -C node_modules/libnice/ --target=0.10.48 rebuild