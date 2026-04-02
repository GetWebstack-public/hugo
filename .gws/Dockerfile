FROM golang:1.20-alpine
RUN apk add --no-cache \
    git \
    nodejs \
    npm \
    gcc \
    g++ \
    musl-dev \
    bash \
    wget \
    libc6-compat
ARG HUGO_VERSION=0.127.0
RUN ARCH=$(uname -m) && \
    case "$ARCH" in \
      x86_64)  HUGO_ARCH="linux-amd64" ;; \
      aarch64) HUGO_ARCH="linux-arm64" ;; \
      *) echo "Unsupported architecture: $ARCH" && exit 1 ;; \
    esac && \
    wget -O hugo.tar.gz "https://github.com/gohugoio/hugo/releases/download/v${HUGO_VERSION}/hugo_extended_${HUGO_VERSION}_${HUGO_ARCH}.tar.gz" && \
    tar -xzf hugo.tar.gz hugo && \
    mv hugo /usr/local/bin/hugo && \
    rm hugo.tar.gz && \
    hugo version
WORKDIR /app
COPY . .
RUN if [ -f package.json ]; then npm install --prefer-offline; fi
EXPOSE 1313
CMD ["hugo", "server", "--bind", "0.0.0.0", "--port", "1313", "--disableFastRender"]
