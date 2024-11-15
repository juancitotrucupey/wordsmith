# Run with:
# docker run -p 8081:80 wordsmith-words
FROM ubuntu AS builder
RUN mkdir -p /home/ubuntu/wordsmith/
WORKDIR /home/ubuntu/wordsmith/
COPY src /home/ubuntu/wordsmith/src
COPY pom.xml /home/ubuntu/wordsmith
RUN apt-get update
RUN apt-get install -y maven \ 
    && mvn verify  
#     && apt-get remove --purge -y maven 
# RUN apt-get install -y default-jre
FROM ubuntu/jre:edge
# RUN mkdir -p /wordsmith/
COPY --from=builder /home/ubuntu/wordsmith/target .
# WORKDIR /target
CMD ["-Xmx8m", "-Xms8m", "-jar", "words.jar"]
