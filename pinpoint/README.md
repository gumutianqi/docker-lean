Pinpoint Docker Compose
===

### Introduction

Github: https://github.com/naver/pinpoint

由于官方没有 build docker 镜像到仓库；所以使用了第三方的镜像

https://github.com/dawidmalina/docker-pinpoint

### What usage

**To run all containers**

> $ docker-compose up -d

**Open the browser**

> http://IP:3080/


### Agent Install

**下载 Agent 应用包**

https://github.com/naver/pinpoint/releases/download/1.6.2/pinpoint-agent-1.6.2.tar.gz

解压到应用程序目录，每个应用程序都需要一个单独的 agent目录

在响应的 Java 应用启动脚本中加入环境变量：

```
JAVA_OPTS: "-javaagent:/assets/pinpoint-agent/pinpoint-bootstrap-1.6.2.jar -Dpinpoint.agentId=app-in-docker -Dpinpoint.applicationName=app"
```

注意：
pinpoint.agentId必须保证唯一，且只能包含（[0-9z-zA-Z] ._-），长度不能超过24位，最好设置有意义的值，agentId会在面板中展示，便于辨识；

pinpoint.applicationName 可与应用名称一致，标识一组应用的集群该值相同