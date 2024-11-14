# Run with:
# docker run -p 8081:80 wordsmith-words
FROM ubuntu
RUN apt-get update
RUN apt-get install -y maven
RUN mkdir -p /home/ubuntu/wordsmith/
WORKDIR /home/ubuntu/wordsmith/
COPY src /home/ubuntu/wordsmith/src
COPY pom.xml /home/ubuntu/wordsmith
RUN mvn verify
WORKDIR /home/ubuntu/wordsmith/target
CMD ["java", "-Xmx8m", "-Xms8m", "-jar", "words.jar"]
