KAFKA
======


.. code-block:: console

    vi /tmp/admin.properties 

    security.protocol=SASL_PLAINTEXT  
    sasl.mechanism=SCRAM-SHA-512  
    sasl.jaas.config=org.apache.kafka.common.security.scram.ScramLoginModule required username="super-user" password="dvYhCnIyimAZ"; 


    ./kafka-topics.sh --bootstrap-server localhost:9092 --describe --topic "app.dsp.dataset-records" --command-config /tmp/admin.properties 
    ./kafka-consumer-groups.sh --bootstrap-server localhost:9092 --group app.news.analytics.ua.production --reset-offsets --to-earliest --topic app.analytics.ua.events.v1 --command-config /tmp/admin.properties --execute 
