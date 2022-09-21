# Example xDS Server

This is an example of a trivial xDS V3 control plane server.
To run the application run the following commands

```
brew install envoy

envoy -c envoy-bootstrap-xds.yaml

go run controlplane
```

If everything works correctly, you should be able to open a browser to [http://localhost:10000](http://localhost:10000) and see Envoy's website.

## Files

* [main.go](main.go) is the example program entrypoint.  It instantiates the cache and xDS server and runs the xDS server process.
* [internal/resource.go](internal/resource.go) generates a `Snapshot` structure which describes the configuration that the xDS server serves to Envoy.
* [internal/server.go](internal/server.go) runs the xDS control plane server.
* [internal/logger.go](internal/logger.go) implements the `pkg/log/Logger` interface which provides logging services to the cache.