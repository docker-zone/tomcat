FROM dingwenxiang0/java:alpine-jdk8

MAINTAINER saruman 624380857@qq.com

ARG TOMCAT_MAJOR=8
ARG TOMCAT_VERSION=8.5.29
ARG TOMCAT_DOWNLOAD_URL=http://mirrors.hust.edu.cn/apache/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz

ENV CATALINA_HOME=/app/tools/tomcat/apache-tomcat
ENV PATH=${PATH}:${CATALINA_HOME}/lib:${CATALINA_HOME}/bin

RUN apk add --no-cache --virtual=build-dependencies wget ca-certificates \
    && mkdir -p /app/tools/tomcat \
    && cd /tmp \
    && wget --header "Cookie: oraclelicense=accept-securebackup-cookie" "${TOMCAT_DOWNLOAD_URL}" \
    && tar -zxf apache-tomcat-${TOMCAT_VERSION}.tar.gz -C /app/tools/tomcat \
    && ln -s /app/tools/tomcat/apache-tomcat-${TOMCAT_VERSION} /app/tools/tomcat/apache-tomcat \
    && apk del build-dependencies \
    && rm -rf /tmp/*

EXPOSE 8080

CMD ["catalina.sh", "run"]