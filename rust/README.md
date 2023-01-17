### Build the workspace

```
docker build --tag workspace:latest -f Dockerfile.workspace .
```

### Publish to artifactory

```
docker build --tag publish:latest -f Dockerfile.publish .
docker run -e CARGO_NET_GIT_FETCH_WITH_CLI=true -e CARGO_REGISTRIES_ARTIFACTORY_INDEX=asdf -e CARGO_REGISTRIES_ARTIFACTORY_TOKEN=asdf publish:latest publish -p kermit
```

