FROM alpine
	
MAINTAINER KJY
	
ENV TOMCAT_MAJOR=9 \
    TOMCAT_VERSION=9.0.30 \
    TOMCAT_HOME=/var/local/tomcat
	
RUN apk update && \
    apk add --update curl && \
    apk add --update openjdk11-jdk && \
    curl -o /tmp/apache-tomcat.tar.gz http://mirror.navercorp.com/apache/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz && \
    tar -C /var/local/ -xf /tmp/apache-tomcat.tar.gz && \
    mv /var/local/apache-tomcat-${TOMCAT_VERSION}/ /var/local/tomcat && \
	# rm -rf ${TOMCAT_HOME}/webapps/* && \
	  rm -rf /tmp/* /var/cache/apk/*
	
#COPY logging.properties ${TOMCAT_HOME}/conf/logging.properties
#COPY server.xml ${TOMCAT_HOME}/conf/server.xml
	
	#VOLUME ["/logs"] #Host /logs에 저장
	EXPOSE 8080
	
	
CMD ["/var/local/tomcat/bin/catalina.sh", "run"]
