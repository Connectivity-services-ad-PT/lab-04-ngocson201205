# Docker Evidence - Lab 04

## Team

- Team name: team-iot
- Service: iot-ingestion
- Image tag: fit4110/iot-ingestion:lab04

## 1. Build Evidence

Command:

```bash
docker build -t fit4110/iot-ingestion:lab04 .
```

Verified locally on 2026-06-15:

```text
exporting to image
naming to docker.io/fit4110/iot-ingestion:lab04 done
```

## 2. Run Evidence

Command:

```bash
docker run -d --rm --name fit4110-iot-lab04 -p 8000:8000 --env-file .env.example fit4110/iot-ingestion:lab04
```

Verified locally on 2026-06-15:

```text
3bebc4b8de655c2872de6ded82a71bd7cee601a48586a1b74291e62e11827a76
```

Container status:

```text
STATUS: Up, healthy
PORTS: 0.0.0.0:8000->8000/tcp
```

## 3. Healthcheck Evidence

Command:

```bash
curl http://localhost:8000/health
```

Result:

```json
{
  "status": "ok",
  "service": "iot-ingestion",
  "version": "0.4.0"
}
```

## 4. Newman Evidence

Command:

```bash
npm run test:local
```

Report path:

```text
reports/newman-lab04-local.html
reports/newman-lab04-local.xml
```

Verified locally on 2026-06-15:

```text
iterations: 1 executed, 0 failed
requests: 11 executed, 0 failed
test-scripts: 11 executed, 0 failed
assertions: 19 executed, 0 failed
average response time: 17ms
```

## 5. Notes

- Known limitation: registry push is not included until the target owner/registry is confirmed.
- Next step for Lab 05: reuse this image in Docker Compose with dependent Smart Campus services.
