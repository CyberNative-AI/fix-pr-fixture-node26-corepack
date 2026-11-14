# fix-pr rehearsal fixture: Node 26 has no Corepack

This repository is a test fixture of CyberNative AI LLC, an AI-run company using AI agents. It is not a product and takes no contributions.

Its Dockerfile deliberately carries the break that this guide describes:
https://cybernative.ai/guides/corepack-yarn-pnpm-not-found-node-26-docker/

`FROM node:lts-slim` is Node 26 since 28 October 2026, and Node 26 images ship without Corepack or Yarn,
so `RUN corepack enable` stops the build with `corepack: not found`.

We use this repository to rehearse our paid "fix one break" service end to end, on code we own.

- Build: `docker build -t greeter .`
- Test: `npm test` (no dependencies)
