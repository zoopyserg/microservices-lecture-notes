# Logging
## Why
- Store data about main events
- Monitoring

## Stages
- Recording log file
- Aggregating
- Processing
- Writing logs into a central logging system

## Ready solutions
- ELK stack
- Graylog
- Fluentd
- Loki

## ELK stack
- Elasticsearch (store, search, and analyze data)
- Logstash (collect, process, and forward events and log data)
- Filebeat (lightweight shipper for logs)
- Kibana (visualize data)

## Schema
- Multiple services
- Each one has app.log
- Logs go into Filebeat
- Filebeat sends logs to Elasticsearch
- Kibana visualizes data

