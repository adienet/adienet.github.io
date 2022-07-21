
https://medium.com/swlh/distributed-tracing-in-micoservices-using-spring-zipkin-sleuth-and-elk-stack-5665c5fbecf


https://www.elastic.co/guide/en/kibana/current/docker.html

Integrasi kibana elasticsearch

1. elastic search
install
docker network create elastic
docker pull docker.elastic.co/elasticsearch/elasticsearch:8.3.2
docker run --name es-node01 --net elastic -p 9200:9200 -p 9300:9300 -t docker.elastic.co/elasticsearch/elasticsearch:8.3.2

2. kibana
docker pull docker.elastic.co/kibana/kibana:8.3.2
docker run --name kib-01 --net elastic -p 5601:5601 docker.elastic.co/kibana/kibana:8.3.2

Resource
https://www.javainuse.com/spring/springboot-microservice-elk
https://auth0.com/blog/spring-boot-logs-aggregation-and-monitoring-using-elk-stack/
https://www.youtube.com/watch?v=5s9pR9UUtAU&list=RDCMUCORuRdpN2QTCKnsuEaeK-kQ&index=1

rizal

5044 filebeat

bikin pipeline
parsing logs with logstash


curl -XPOST "http://localhost:9200/_search" -d'   
  {
     "query": {
       "match_all": {}
     }
  }'



https://morioh.com/p/d24be2d8b9b2
1. wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
2. sudo apt-get update
sudo apt-get install apt-transport-https
3. echo "deb https://artifacts.elastic.co/packages/8.x/apt stable main" | sudo tee -a /etc/apt/sources.list.d/elastic-8.x.list
deb https://artifacts.elastic.co/packages/8.x/apt stable main
4. sudo apt-get update && sudo apt-get install elasticsearch
start elasticsearch
sudo systemctl daemon-reload
sudo systemctl enable elasticsearch.service
5. sudo nano /etc/elasticsearch/elasticsearch.yml
uncomment
https://discuss.elastic.co/t/failed-to-start-elasticsearch-usr-lib-systemd-system-elasticsearch-service-disabled-vendor-preset-disabled/309514/2
cluster.name: my-application
node.name: node-1
network.host: 127.0.0.1
http.port: 9200

sudo systemctl start elasticsearch.service
untuk lihat error log start nya di 
tail -f /var/log/elasticsearch/elasticsearch.log