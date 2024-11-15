# If thew /static folder is mounted run with:
# docker run -p 8080:80 -v /home/agentsmith/Desktop/Trucupey_PP/Containers/Docker/Course/self_paced_intrp_2_docker/wordsmith-example/wordsmith/web/static:/home/wordsmith/static wordsmith-web-multistage
# If the static folder is not mounted run with:
# docker run -p 8080:80 wordsmith-web-complete
FROM golang AS builder
RUN mkdir -p /home/wordsmith/
WORKDIR /home/wordsmith/
COPY dispatcher.go /home/wordsmith
RUN go build dispatcher.go
FROM ubuntu
RUN mkdir -p /home/wordsmith/
WORKDIR /home/wordsmith/
COPY --from=builder /home/wordsmith/dispatcher /home/wordsmith/
COPY /static /home/wordsmith/static
CMD [ "./dispatcher" ]

