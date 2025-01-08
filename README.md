
# Prometheus Example 

This repo demonstrates setting up Prometheus monitoring.

## Installation

1. Download the Prometheus binary
2. Run `./prometheus --config.file=prometheus.yml`

## Exposing Metrics

Use client libraries to instrument your app and expose metrics:

```python
from prometheus_client import start_http_server, Summary

REQUEST_TIME = Summary('request_processing_seconds', 'Time spent processing request')

@REQUEST_TIME.time()
def process_request(t):
    time.sleep(t)

start_http_server(8000)
```

## Visualization 

Grafana can be used to visualize the collected metrics.
