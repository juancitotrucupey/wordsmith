# Run with:
# docker run -p 8080:80 -v /home/agentsmith/Desktop/Trucupey_PP/Containers/Docker/Course/self_paced_intrp_2_docker/wordsmith-example/wordsmith/web/static:/home/wordsmith/static wordsmith-web
FROM golang
RUN mkdir -p /home/wordsmith/
WORKDIR /home/wordsmith/
COPY dispatcher.go /home/wordsmith
RUN go build dispatcher.go
CMD [ "./dispatcher" ]

