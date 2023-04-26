FROM openjdk:8 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/kemdej/bootcamp01.git
RUN cd bootcamp01 && mvn install

FROM tomcat:8-jre11
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from BUILD_IMAGE bootcamp01/target/vprofile-v2.war  /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8O80
CMD ["catalina.sh", "run"]
