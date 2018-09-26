# Puppet for dockerized docker-agent

This for your Puppet inspiration. Final implementation is up to you:

```
class { 'docker':
  version => 'latest',
}->
docker::image { 'monitoringartist/dockbix-agent-xxl-limited':
  image_tag => 'latest',
}->
docker::run { 'docker-agent':
  image            => 'monitoringartist/dockbix-agent-xxl-limited',
  extra_parameters => ['--restart=unless-stopped'],
  privileged       => true,
  net              => 'host',
  volumes          => ['/:/rootfs'],
  env              => [
    'ZA_Server=<ZABBIX SERVER IP/DNS NAME>',
  ],
}
```

Summary:
* 1000+ [GitHub](https://github.com/madrum-x/) stars
* 6000+ [Grafana dashboard](https://grafana.net/monitoringartist) downloads
* 800 000+ [Docker image](https://hub.docker.com/u/monitoringartist/) pulls

