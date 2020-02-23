FROM golang:latest
LABEL maintainer "Anshu Prateek <http-echo@anshuprateek.com> (@anshprat)"

RUN export GOROOT=/go
RUN mkdir /app
ADD . /app/
ADD . /go/src/github.com/hashicorp/http-echo
WORKDIR /app
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -a -installsuffix cgo -o http-echo
CMD ["/bin/bash"]

FROM scratch
EXPOSE 5678
ADD https://curl.haxx.se/ca/cacert.pem /etc/ssl/certs/ca-certificates.crt
COPY --from=0 /app/http-echo /
CMD ["/http-echo"]
