The application follows a microservices architecture, where each
service is responsible for a distinct piece of functionality. The services
communicate via REST APIs, and the system is orchestrated using
Docker Compose for local development and testing. 
Step 1: Clone the Repository
Start by cloning the application’s repository to your local machine.
# git clone https://github.com/ Charankamma06/flight_app
# git cd flight_app

Step 2: Configure Environment Variables
Ensure that all required environment variables are set up. These
variables might include database credentials, API keys, and other
configuration settings.
• Create a .env file in the root directory of your project (if not
already present) and populate it with the necessary variables.
Step 3: Build Docker Images
Navigate to the root directory of your project (where the
dockercompose.yml file is located) and build the Docker images
for each microservice.
# docker-compose build
This command will look for Dockerfile in each service's directory,
build the images, and tag them appropriately.
Step 4: Start the Services
Now, start the application by running the following command:
# docker-compose up
Without Detached Mode: This will start all services and display the
logs in your terminal.
With Detached Mode: To run the services in the background, use the
-d flag:
# docker-compose up -d
Step 5: Verify the Services
After running docker-compose up, Docker Compose will start the
following:
• Microservices: Each service (e.g., User Service, Product
Service, etc.) in its own container.
• Database: If you have a database service, it will also be started.
• API Gateway: The API Gateway (e.g., NGINX) will be
configured to route requests to the appropriate services.
Check the status of the services:
# docker-compose ps
Step 6: Access the Application
Once all services are running, you can access the application through
the API Gateway or the service endpoints.
• API Gateway: If you have configured an API Gateway, you can
access the application via the gateway’s URL (e.g.,
http://localhost:8080).
• Direct Access: If no API Gateway is configured, you can access
each service directly using their respective ports defined in the
docker-compose.yml file.
Step 8: Stop the Services
To stop the services, run:
# docker-compose down
Step 9: Clean Up
If you want to remove all images, containers, and networks related to
the project, you can run:
# docker-compose down --rm all –volumes 
