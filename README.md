**Stream Processing Project for E-Commerce Company to Identify Product Purchased and Click Attributed to the Purchase**

This project uses Apache Flink and Apache Kafka to build a stream processing pipeline that identifies product purchases and attributes them to clicks. The architecture is as follows:

1. **Application:** A click simulator application generates click event data using the Faker library.
2. **Queue:** Click event data is sent to Kafka topics.
3. **Stream processing:** Flink reads data from Kafka topics and performs the following steps:
   - Stores click data in cluster state.
   - Enriches checkout data with user data from PostgreSQL.
   - Left joins checkout data to click data to determine if the purchase can be attributed to a click.
   - Logs enriched and attributed data to a PostgreSQL sink table.
4. **Monitoring and alerting:** Flink metrics are pulled by Prometheus and visualized using Grafana.

This project will enable the e-commerce company to better understand the customer journey and identify which marketing campaigns are driving sales.
