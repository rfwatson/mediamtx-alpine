# mediamtx-alpine

Dockerfile which bundles
[MediaMTX](https://github.com/bluenviron/mediamtx) with curl in an Alpine
container.

The image version maps directly to the MediaMTX version.

[![Trivy Scan](https://github.com/rfwatson/mediamtx-alpine/actions/workflows/build.yml/badge.svg?branch=main)](https://github.com/rfwatson/mediamtx-alpine/actions/workflows/build.yml)
[![Docker Image](https://img.shields.io/badge/image-ghcr.io%2Frfwatson%2Fmediamtx--alpine-blue)](https://ghcr.io/rfwatson/mediamtx-alpine)
![Version](https://img.shields.io/badge/version-1.13.1-blue)

## FAQ

#### Why?

When deploying in a containerized environment, curl or some other HTTP client
is required in the MediaMTX container for running health checks.

The provided MediaMTX Docker image is a scratch image that has no additional
tooling.
