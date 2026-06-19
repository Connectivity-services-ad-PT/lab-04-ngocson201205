# Docker Readiness Checklist

## Dockerfile

- [x] Uses a suitable base image.
- [x] Defines `WORKDIR`.
- [x] Copies dependency files before source files to use Docker layer cache.
- [x] Defines `EXPOSE 8000`.
- [x] Defines `CMD`.
- [x] Includes `HEALTHCHECK` for `GET /health`.
- [x] Runs as a non-root user.
- [x] Does not contain real secrets.

## Runtime

- [x] Container starts successfully.
- [x] Port mapping is correct: `8000:8000`.
- [x] `/health` returns `200`.
- [x] Startup logs are available through `docker logs`.
- [x] Runtime config is provided through environment variables.

## Testing

- [x] Postman/Newman collection runs against the Docker container.
- [x] Newman reports are generated in `reports/`.
- [x] Functional tests pass.
- [x] Auth tests pass on local/container.
- [x] Negative tests pass on local/container.
- [x] Boundary tests pass on local/container.

## Evidence

- [x] Docker build verified.
- [x] Docker run verified.
- [x] `curl /health` verified.
- [x] Newman HTML/XML reports generated.
- [x] Image tag follows the lab convention: `fit4110/iot-ingestion:lab04`.
