# Monitoring

## Why
- Knowing system status
- Knowing service status
- Notifications

## Types
- System monitoring
- Metrics monitoring
- Business monitoring

## Solutions
- Prometheus
- Elastic Stack
- InfluxDB
- Zabbix

## Prometheus
- Mutli dimensional data model
- Built in alteriing
- PromQL
- Exporters
- Client libs (Ruby, Python, Go, Java, etc)

Prometheus is usually used with Grafana.

## Data types in Prometheus
- Counter
- Gauge
- Histogram
- Summary

## Metrics selection
- System
  - CPU
  - Memory
  - Network
  - Filesystem
- API
  - Request Rate
  - Response Time
- Microservice
  - Request Rate

## Graphana
It needs to know source of data (Prometheus)
It has pre-made dashboards on Grafana website
To use them you need to specify their ID and load them.

## Integrating Prometheus with Ruby
```ruby
gem 'client_ruby'
```

```ruby
use Rack::Runtime
use Rack::Deflater
```

The terminology is similar to New Relic.
But here we manually set what we want to monitor.
