# 前言
	安装了tomcat+orace java 8+alpine3.7的镜像。

# 使用指南
	docker run -d -p 8080:8080 --name tomcat dingwenxiang0/tomcat:8.5-alpine-jre8
	docker run -d -p 8080:8080 --name tomcat dingwenxiang0/tomcat:8.5-alpine-jdk8