# Full Stack Web Project with Microservices
This project is a full-stack web application project
and it was created with Java and React.<br/> 
Spring Cloud was used in this project to create
the microservice architecture. Detailed explanations
of the services in the microservice architecture 
are explained in the readme files of the services.

## Architectural Design
<p align="center">
    <img src="architectural_design.jpeg"  />
</p>

## Subject Of Project
CineVision App is an online cinema ticket sale website. The purpose of 
this website is to provide ease of buying tickets for those who 
want to watch movies in the cinema. People can display movies in the theaters or
upcoming movies. They can see the movie details and learn the plot,
the actors, the release date, and so on. On this detail page, people can choose the city
and movie theater where they want to watch the film. After this selection, they can automatically
redirect to the payment page. On this payment page, they can see ticket count and type such as 
student and adult. Then, they can choose the chairs they will sit on in the movie theater.
Finally, they complete payment process after entering information
of credit card, email, name,& surname.
If the payment is successful, the ticket details are sent to the email which 
entered by the user.
If people want to share their opinions about the movie, they can see comments on the movie detail page.
However, People must create an account to comment on movies. Only admins
can add a movie, actor, or director to the system. This authorization process is controlled
with a Jwt token.

## Technologies Of Project
There are many technologies in this project. These are:
<h5> Backend Tech: </h5>
<ul>
    <li>Java17+</li>
    <li>Spring Boot 2.7.0 </li>
    <li>Spring Cloud</li>
    <li>Spring Data Jpa</li>
    <li>Spring Security</li>
    <li>Lombok</li>
    <li>WebClient</li>
    <li>Apache Kafka</li>
    <li>Jwt</li>
    <li>Java Mail Sender</li>
    <li>Zipkin</li>
    <li>Resilience4j</li>
    <li>PostgreSql</li>
    <li>MongoDB</li>
    <li>Redis</li>
    <li>Docker</li>
</ul>
<h5> Frontend Techologies </h5>
<ul>
    <li>JavaScript</li>
    <li>React</li>
    <li>Bootstrap</li>
    <li>Redux</li>
</ul>

## Project UI

https://user-images.githubusercontent.com/79381882/194945895-f7e2d2d2-4899-4ade-8c79-ecb647949ffd.mp4

<h4>Main Page</h4>

<img src="homa_page.jpg">

[For more UI Images](https://github.com/Parth018/CineVision-Java-React/tree/main/frontend)

## Usage Of Technologies In Project
There are 5 services in this project and each service 
is written with N-layered architecture. Spring Cloud
is used for microservice infrastructure.
Netflix Eureka Server was used to create the Eureka server. This 
eureka server contains a movie service, user service email service
eureka clients, and an api-gateway service. In addition,
Zipkin and Sleuth were used to monitor cross-service logs. Also,
Resilience4j is used as a Circuit Breaker.
<br>
<br>
In the Api Gateway, Spring Cloud Gateway was used for managing
requests.
<br>
<br>
In the Eureka Server, Netflix Eureka Server was used. And Spring
Security was used to secure the Eureka server.
<br>
<br>
WebFlux was used to communicate between Movie and User Services.
And, Apache Kafka was used for asynchronous communication
between Movie and Email Services.
<br>
<br>
In the User Service, MongoDB is used as a database. Spring Security
was used to encrypt users' passwords and generate Jwt tokens.
<br>
<br>
In the Movie Service, PostgreSQL was used as the database and Spring Data JPA
was used. Webflux and Apache Kafka were used to communicate with other services.
Resilience4J Circuit Breaker was used here. Displaying and coming soon movies
are cached using Redis.
<br>
<br>
In the Email Service, Apache Kafka was used for receiving the 
messages from the Movie Service. Java Mail Sender and FreeMarker templates 
were used for creating email templates and sending emails.
<br>
<br>
PostgreSQL, MongoDB, Apache Kafka, and Zipkin run as Docker containers
in the docker-compose.yml file.

On the front side, JavaScript and React were used. Also,
Axios was preferred to send requests to the backend. For state management,
Redux was used. For, the design of the UI, Bootstrap, and CSS are used.

## How can I use the Project?
Download the source code of the project. Open this project with your 
favorite IDE. Make sure Java 17, Node.js, and Docker are installed on
your computer. And, follow these steps:

<ol>
    <h3> <li>Run docker-compose.yml file</li> </h3>
<p>
This docker composes file is necessary to run Postgre, mongo, 
Kafka etc. Open cmd in the project directory and type

    docker-compose up -d

command to run the containers.
</p>
<h3> <li>Run Eureka Server</li> </h3>
<p>
    Go to the EurekaServerApplication class which is in the eureka-server module
and run this class to create a eureka server. If you want to display
the eureka server panel, you can go to <b>localhost:8080/eureka/web </b> or
<b>localhost:8761</b> addresses. Then, enter username= <b>eureka</b> and 
password= <b>password</b>.

</p>

 <h3> <li>Run Api Gateway</li> </h3>
<p>
   To forward the requests to the relevant services, Gateway must be 
run. Go to the ApiGatewayApplication class which is in the api-gateway modules
and run this class. If you want to check that the api-gateway is registered 
to the eureka server, you can display the eureka server panel.
</p>

 <h3> <li>Run Movie Service</li> </h3>
<p> 
To run movie service go to movie service module. And, run 
MovieServiceApplication class.
</p>

<h3> <li>Run User Service</li> </h3>
<p> 
In the user service module, find the UserServiceApplication class and run this
class.
</p>
<h3> <li>Run Email Service</li> </h3>
<p> 
The emailServiceApplication class is in the email service module. To run the email service module,
run this class.
</p>

<h3> <li>Run Email Service</li> </h3>
<p> 
The emailServiceApplication class is in the email service module. To run the email service module,
run this class. If this module is started successfully, you can view 
all running services in the eureka server using with eureka panel which is
running on localhost:8761 or localhost:8080/eureka/web.
</p>
<h5>Important Note: <br>
Change mail configurations in the application.yml file with your own configurations.
</h5>

<h3> <li>Start React (Frontend) Application</li> </h3>
<p> 
Go to the frontend package which is the location of the frontend code.
Firstly, type

    npm install

command in cmd for downloading package.json dependencies. Then, To start
the React app, type

    npm start

command. After that, npm will start your React Application
on <b> localhost:3000 </b>.

</p>


</ol>

