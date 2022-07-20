
https://medium.com/swlh/distributed-tracing-in-micoservices-using-spring-zipkin-sleuth-and-elk-stack-5665c5fbecf


https://www.elastic.co/guide/en/kibana/current/docker.html

Integrasi kibana elasticsearch

1. elastic search
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
