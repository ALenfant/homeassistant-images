# Development Notes
For personal usage, they might help you as well!

## Build Docker image locally
```bash
docker build \
  -t local/base-nodejs-image \
  .
```

## Run container
```bash
docker run \
  --rm \
  local/base-nodejs-image
```