# Command: docker build . -t be-example && docker run -p 8080:8080 be-example
FROM golang:latest
WORKDIR /usr/src/app
ENV PATH=/usr/local/go/bin REQUEST_ORIGIN=http://localhost:5000
EXPOSE 8080
COPY . .
RUN go build
CMD ["./server"]