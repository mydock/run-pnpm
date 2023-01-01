# docker-run-pnpm

A ONBUILD docker for Cloud Run

## alpha2

* Same as alpha1 except node is installed before fetch.
* This is a workaround for https://github.com/pnpm/pnpm/issues/5865

```dockerfile
FROM ghcr.io/mydock/run-pnpm:alpha2

ADD . .

RUN pnpm build
```

## alpha1

```dockerfile
FROM ghcr.io/mydock/run-pnpm:alpha1

ADD . .

RUN pnpm build
```
