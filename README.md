# cinema-basket-ticket
A simple  Microservice project for ordering ticket to cinema movies

#About Services

**Admin Service** => Manage users and define ticket and show statistics

**Ticket Service** => List of ticket, recommend ticket and more ticket list

**Order Service** => Order Ticket and return redirect to gateway

**Finance & Payment Service** => Do jobs around payment services and financial calculation

**Notification Service** => Send Notification such as Email and Sms to client about ordering process and payment process and marketing

**Admin UI Service** => Admin panel UI Service use angular framework

**App UI** => App Frontend and html template

# How to Run Services

**Important Tips** => we have two way to run these services you can use 
**Service Mesh** or **Api Gateway** for manage services contract or authorization 


if you wanna run application with _Service Mesh_ you must comment _kong_api_gateway_ service
else you must comment _Istio_ service 

**How to run application Services**
at first step you must select **SERVICE MESH** or **API GATEWAY**

in second step run application services as containers with docker, you must run under command

``` docker-compose up -f docker-compose-api-gateway.yml -d ```

or 

``` docker-compose up -f docker-compose-service-mesh.yml -d ```

in third step you must run application configuration and migrating mysql db tables

``` docker-compose exec admin_service php artisan migrate  ```

