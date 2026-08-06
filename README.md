## Dockerfile
```bash
FROM ubuntu:24.04
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y --no-install-recommends curl ca-certificates && \
    rm -rf /var/lib/apt/lists/*
WORKDIR /app
COPY --chmod=755 ./book ./book
ENV AWS_REGION="ap-northeast-2"
ENV TABLE_NAME="wskorea26-data-table"
EXPOSE 8080
CMD ["./book"]
EOF
```
