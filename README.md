# springboot-ELK-demo

### About this project
- This project is a demo, on how to see the logs of a spring boot project into the Kibana portal

### How part
- We are using the docker images for running the ELK stack
- but here instead of Logstash, we are using the filebeat to push the logs to Elastic Search
- The Flow is like blow
  - Filebeat reads the logs and pushes it to the Eleastic Search server
  - Kibana queries the elasticsearch data via REST APIS, and shows in the UI

### How to check the logs in the kibana
- Open terminal 
- Go into the elk-stack folder
- Run the `docker compose up -d`
- it will create and start containers (Eleastic search, filebeat, kibana)
- Then Open the kibana `http://localhost:5601/`
- Go to the StackManagement > Index Management > enable include hidden indices
- Then you can see an index with format  ".ds-springboot-log-*"
- The go into the DataView > create data view > give the name and index pattern (ex: springboot-logs-*), select the timestamp
- Then if you go to the Discover select the Data view > then you should be able to see the logs.
