FROM amd64/golang:1.12-alpine

COPY golang-webserver ./

RUN chmod +x golang-webserver

EXPOSE 8080

ENTRYPOINT ["./golang-webserver"]