FROM golang:latest AS build
WORKDIR /go/src/app
COPY ./main.go .
COPY ./go.mod .
COPY ./go.sum .
RUN CGO_ENABLED=0 go build -o adtech

FROM alpine
COPY --from=build /go/src/app/adtech /tmp
CMD ["/tmp/adtech"]
