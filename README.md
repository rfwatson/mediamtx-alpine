# mediamtx-alpine

Dockerfile which bundles
[MediaMTX](https://github.com/bluenviron/mediamtx) with curl in an Alpine
container.

The image version maps directly to the MediaMTX version.

[![Trivy Scan](https://github.com/rfwatson/mediamtx-alpine/actions/workflows/build.yml/badge.svg?branch=main)](https://github.com/rfwatson/mediamtx-alpine/actions/workflows/build.yml)
[![Docker Image](https://img.shields.io/badge/image-ghcr.io%2Frfwatson%2Fmediamtx--alpine-blue)](https://ghcr.io/rfwatson/mediamtx-alpine)
![Version](https://img.shields.io/badge/version-1.12.2-blue)

## FAQ

#### Why?

When deploying in a containerized environment, curl or some other HTTP client
is required in the MediaMTX container for running health checks.

The provided MediaMTX Docker image is a scratch image that has no additional
tooling.

#### Why base the final image on Alpine, instead of copying curl and mediamtx binaries to another scratch image?

The default build of curl as installed by Alpine is dynamically linked and does
not run on a scratch image due to lack of supporting libraries.

On the surface the size difference between the two images is about 13MB. It
would probably be possible to use a static build of curl instead, but that
would have trade-offs in terms of build complexity and supply chain trust.
