# Ansible for dockerized docker-agent

This for your Ansible inspiration. Final implementation is up to you:

```
# Used Core Docker module - http://docs.ansible.com/ansible/docker_module.html
- name: docker-agent container
  docker:
    name: docker-agent
    image: monitoringartist/dockbix-agent-xxl-limited:latest
    restart_policy: unless-stopped
    state: started
    pull: always
    net: host
    privileged: true
    volumes:
      - /:/rootfs
      - /var/run:/var/run
    env:
        ZA_Server: <ZABBIX SERVER IP/DNS NAME>     
```

Summary:
* 1000+ [GitHub](https://github.com/madrum-x/) stars
* 6000+ [Grafana dashboard](https://grafana.net/monitoringartist) downloads
* 800 000+ [Docker image](https://hub.docker.com/u/monitoringartist/) pulls

