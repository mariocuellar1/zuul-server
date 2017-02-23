# README

## Spring Boot Zuul Server

Zuul is the front door for all requests from devices and web sites to the backend of the Netflix streaming application. As an edge service application, Zuul is built to enable dynamic routing, monitoring, resiliency and security. It also has the ability to route requests to multiple Amazon Auto Scaling Groups as appropriate.

This project is a simple but functional Zuul Server using Spring Boot with simple HTTP Basic Authentication. This project requires a [Microservice](https://github.com/mariocuellar1/customers-microservice), [oAuth Server](https://github.com/mariocuellar1/oauth-server-opaque) and [Eureka Server](https://github.com/mariocuellar1/eureka-server)

### How to install
It's an eclipse project, just import it and run.

### Parameters & Configuration
* **application.yml**
  * *Zuul routing params*: See more at [Routing and Filtering](https://bushkarl.gitbooks.io/spring-cloud/content/spring_cloud_netflix/router_and_filter_zuul.html)
  * **eureka.client.serviceUrl.defaultZone** : Eureka server URI(s)
  * **server.port** : Server Port

### How to test

Before you run this server you need to configure and start Eureka Server (or cluster) please make a look to [Eureka Server](https://github.com/mariocuellar1/eureka-server). 
You also have to configure and start oAuth Server, please make a look to [oAuth Server using JWT Token](https://github.com/mariocuellar1/oauth-server-jwt)
This Server tries to register itself in Eureka Server, if Eureka server is down throws "java.net.ConnectException: Connection refused: connect" error, but Microservice works.

1. Configure application (application.yml above)
2. Start Routing Microservice please see how to [Microservice](https://github.com/mariocuellar1/customers-microservice)
3. Start Zuul Server [rigth-clic, run  :) ]
3. Import postman project *ZuulAndCustomerMicroserviceTest.postman_collection.json* to postman app
   * Test "Get all customers using Zuul": List all customers, before you need to get a oauth valid token using Postman test "Token - password" and update it in Authorization header.
   * Test "Add Customers Zuul": Add new customer, before you need to get a oauth valid token using Postman test "Token - password" and update it in Authorization header
      
And you Done !!!!  

### Notes:
- I use postman to test 'cause it's what I usually do :) , if you want, modify this readme adding other ways, CURL, junit, simple java ó whatever.
- Please feel free to add/modify/correct/update any part of this content as necessary

### Related Projects
- [oAuth Server](https://github.com/mariocuellar1/oauth-server-opaque)
- [Microservice](https://github.com/mariocuellar1/customers-microservice)
- [Eureka Server](https://github.com/mariocuellar1/eureka-server)

### Other Projects:
- [Basic Resource Server using oauth and opaque token](https://github.com/mariocuellar1/basic-resource-server-opaque)
- [oAuth Server using JWT Token](https://github.com/mariocuellar1/oauth-server-jwt)
- [Basic Resource Server validating JWT Token](https://github.com/mariocuellar1/basic-resource-server-jwt)
- [Vehicles Microservice](https://github.com/mariocuellar1/vehicles-simple-microservice)
