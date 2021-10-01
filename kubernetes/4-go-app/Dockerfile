FROM golang:1.7.3 as build
WORKDIR /app
COPY main.go .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main

FROM alpine:3.7 as final
WORKDIR /app
COPY --from=build /app/main .
CMD ["./main"]