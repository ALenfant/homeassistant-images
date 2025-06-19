ARG BUILD_FROM=ghcr.io/hassio-addons/base:17.2.5
# https://github.com/hassio-addons/addon-base/releases
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

ARG TARGETPLATFORM

RUN echo "Building for $TARGETPLATFORM"

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Environment configuration
ENV YARN_VERSION 1.22.22

ENV YARN_VERSION 1.22.22
COPY --from=node:20-alpine /opt/yarn-v$YARN_VERSION /opt/yarn-v$YARN_VERSION
COPY --from=node:20-alpine /usr/local/bin/node /usr/local/bin/node
COPY --from=node:20-alpine /usr/local/lib/node_modules/ /usr/local/lib/node_modules/
COPY --from=node:20-alpine /usr/local/include/node/ /usr/local/include/node/

RUN ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm \
    && ln -s /usr/local/lib/node_modules/npm/bin/npx-cli.js /usr/local/bin/npx \
    && ln -s /usr/local/lib/node_modules/corepack/dist/corepack.js /usr/local/bin/corepack \
    && ln -s /opt/yarn-v$YARN_VERSION/bin/yarn /usr/local/bin/yarn