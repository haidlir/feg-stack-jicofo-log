
# FEG STACK for Jicofo Log
This repository is intended as log analysis solution for Jitsi's Jicofo using :
- Fluent.d
- Elasticseach
- Grafana

## How To
### Change password
- Elastic (see the docker-compose.yaml)
```
      ELASTIC_PASSWORD: changeme
```
- Grafana (see the docker-compose.yaml)
```
      - "GF_SECURITY_ADMIN_PASSWORD=changeme"
```
- Dont't forget to update the configuration file
  - elasticsearch/conf/elasticsearch.yml
  - fluentd/conf/fluent.conf
  - kibana/conf/kibana.yml

### Add more plugin
- Fluent.d Dockerfile (see the fluentd/Dockerfile)
```
RUN ["gem", "install", "fluent-plugin-elasticsearch", "--no-document", "--version", "3.5.2"]
```

### Build, Up, Down, Restart
```
$ ./build.sh
$ ./up.sh
$ ./down.sh
$ ./restart.sh
```
