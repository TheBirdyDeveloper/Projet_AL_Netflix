FROM ubuntu:14.04
RUN apt-get update && apt-get install -y openjdk-7-jdk git libgradle-core-java
RUN git clone https://github.com/Netflix/recipes-rss
RUN export APP_ENV=dev
WORKDIR /recipes-rss
RUN ./gradlew clean build
CMD java -Deureka.serviceUrl.default=http://172.17.0.2:8080/eureka/v2/ -jar rss-edge/build/libs/rss-edge*SNAPSHOT.jar
EXPOSE 9090 9092
