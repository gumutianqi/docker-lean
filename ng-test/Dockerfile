FROM nginx:latest

## 环境变量
ENV VERSION=1.0.0 \
    AUTHOR=LarryKoo \
    EMAIL=gumutianqi@gmail.com \
    VOLUME_BASE=.

## 改变默认首页内容
COPY ./index.html /usr/share/nginx/html/

VOLUME $VOLUME_BASE/data

EXPOSE 80

WORKDIR /app

RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*

HEALTHCHECK  --interval=5s --timeout=3s CMD curl http://localhost/ || exit 1

