FROM openjdk:11 AS BUILDER_IMAGE
RUN apt update && apt install maven -y
RUN git clone --branch docker https://github.com/Tershoww/vprofile-project.git
RUN cd vprofile-project && mvn install

FROM tomcat:9-jre11
LABEL "Project"="Vprofile"
LABEL "Author"="Tershoww"
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILDER_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# Not necessary because this image is already exposing this port -> check doc from this image in dockerhub
EXPOSE 8080

# To run tomcat server. Check the documentation of this image in docekrhub to find this command
# It's by default too, so it's not necessary
CMD ["catalina.sh","run"]