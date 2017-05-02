FROM java:8

RUN apt-get update && \
    apt-get install -y \
	git \
	wget

WORKDIR /usr/local/

RUN rm -rf tomcat*

RUN wget --no-check-certificate -O tomcat.tar.gz http://repo2.maven.org/maven2/org/apache/tomcat/tomcat/8.5.0/tomcat-8.5.0.tar.gz > /dev/null 2>&1

RUN tar -xzvf tomcat.tar.gz
RUN rm -rf tomcat.tar.gz
RUN mv apache-tomcat-8.5.0/ tomcat8

RUN wget -O /usr/local/tomcat8/webapps/eureka.war -q http://central.maven.org/maven2/com/netflix/eureka/eureka-server/1.3.7/eureka-server-1.3.7.war

EXPOSE 8080
WORKDIR /usr/local/tomcat8
CMD ["bin/catalina.sh", "run"]
