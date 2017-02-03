fluent-plugin-gelf
==================

Example usage

```
<source>
  type syslog
  tag graylog2
</source>
<source>
  type tail
  format nginx
  path /var/log/nginx/access.log
  tag graylog2.nginx
</source>
<match graylog2.**>
  type copy
  <store>
    type gelf
    host 0.0.0.0
    port 12201
    flush_interval 5s
  </store>
  <store>
    type stdout
  </store>
</match>
```