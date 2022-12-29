# docker-run-pnpm

A ONBUILD docker for Cloud Run


## alpha1

```dockerfile
FROM ghcr.io/mydock/run-pnpm:alpha1

ADD . .

RUN pnpm build
```
