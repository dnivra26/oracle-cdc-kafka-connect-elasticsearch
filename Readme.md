/scripts/go_sqlplus.sh /scripts/oracle_setup_docker.sql


curl -s -X POST -H 'Content-Type: application/json' --data @SimpleOracleCDC.json http://localhost:8083/connectors

curl -s -X POST -H 'Content-Type: application/json' --data @ElasticsearchConnectorConfig.json http://localhost:8083/connectors


curl -X PUT localhost:8083/connectors/simple-elasticsearch-connector/config -H "Content-Type: application/json" --data @ElasticsearchConnectorConfig.json 

curl -s -X DELETE http://localhost:8083/connectors/simple-elasticsearch-connector

kafka-avro-console-consumer --bootstrap-server broker:29092 --property schema.registry.url="http://schema-registry:8081" --topic ORCLCDB.C__MYUSER.EMP --from-beginning