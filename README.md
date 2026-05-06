# boe-hello

A minimal Envoy dynamic module filter using [jisr](https://github.com/dio/jisr).

## Build

```sh
CGO_ENABLED=1 go build -trimpath -buildmode=c-shared -o hello.so ./cmd
```

## Usage in envoy.yaml

```yaml
http_filters:
  - name: hello
    typed_config:
      "@type": type.googleapis.com/envoy.extensions.filters.http.dynamic_modules.v3.DynamicModuleFilter
      dynamic_module_config:
        name: hello
      filter_name: hello
```
