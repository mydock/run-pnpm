FROM ubuntu

WORKDIR /app

RUN apt-get update && apt-get install -y --no-install-recommends \
    nano curl ca-certificates \
    && rm -rf /var/lib/apt/lists/*

ENV PNPM_HOME=/pnpm PATH="/pnpm:${PATH}"

RUN curl -fsSL "https://github.com/pnpm/pnpm/releases/latest/download/pnpm-linuxstatic-x64" -o /bin/pnpm; chmod +x /bin/pnpm;

ONBUILD COPY pnpm-lock.yaml ./

ONBUILD RUN pnpm fetch

ONBUILD COPY package.json .node-version ./

ONBUILD RUN pnpm -g env use $(cat .node-version)

ONBUILD RUN pnpm install

CMD ["pnpm", "start"]
