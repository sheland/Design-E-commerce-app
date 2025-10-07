# Design-E-commerce-app (in Google Cloud)
Simple design solution for creating an E-commerce app 

### Requirements for E-commerce app must include the following:
1. User registration and authentication
2. Product catalog
3. Shopping cart
4. Inventory management
5. Data analytics and machine learning

### High level architecture:
![unnamed-4](https://github.com/user-attachments/assets/cd27e407-e676-47b2-b9cb-c26cac87b466)

### Explaination 
* At a high level, add load balancer in front of the frontend layer
  * used CloudRun for frontend
* Backend includes microservices for each service
    * can scale better with microservices in a decoupled environment
* For DBm used Firestore for document data and user profile
* For inventory, product, cart and order data, can use Cloud SQL, AlloyDB or Cloud spanner
* All data is streamed into the messagaging service PubSub
* Stream processing is done in datadlow, a serverless stream processing  service and then store the clean data into a serverless data warehouse BigQuery
* From there you can use data for machine learning and buiness intelligence 

