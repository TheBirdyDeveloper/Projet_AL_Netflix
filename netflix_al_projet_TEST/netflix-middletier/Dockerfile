FROM ubuntu:14.04
RUN apt-get update && apt-get install -y openjdk-7-jdk git libgradle-core-java
RUN git clone https://github.com/Netflix/recipes-rss
WORKDIR /recipes-rss
RUN ./gradlew clean build
WORKDIR /recipes-rss
RUN export APP_ENV=dev
RUN ./gradlew clean build
CMD java -Deureka.serviceUrl.default=http://172.17.0.2:8080/eureka/v2/ -jar rss-middletier/build/libs/rss-middletier*SNAPSHOT.jar

EXPOSE 9191 9192
