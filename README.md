# sit323-737-2023-t1-prac5d

Explanation-:
This code is a Docker Compose file that defines two services, "web" and "db", and a custom network called "my-network". The networks section defines the custom network, and each service is configured to use the network with the networks section.
Here's how the network configuration works:
•	my-network is a custom Docker network with a subnet of 172.28.0.0/16 and a gateway of 172.28.0.1.
•	The web service is configured to use the my-network network with the networks section. The ipv4_address option is set to 172.28.5.2, which sets a specific IP address for the container to use on the my-network network.
•	The db service is also configured to use the my-network network with the networks section. The ipv4_address option is set to 172.28.5.3, which sets a specific IP address for the container to use on the my-network network.
With this network configuration, the web and db containers will be able to communicate with each other over the my-network network using their assigned IP addresses. This allows the services to be isolated from other containers on the host machine or on other networks. The containers can also be accessed by their container names if needed, since Docker automatically maps container names to their IP addresses on the custom network.

The docker-compose up command is used to start the Docker Compose application defined in the docker-compose.yml file. When you run this command, Docker Compose will do the following:
1.	Check if the images for the services defined in the docker-compose.yml file already exist locally. If not, Docker Compose will build the images using the Docker files specified in the build section of the services.
2.	Create a new Docker network (if one doesn't already exist) for the application based on the network configuration specified in the docker-compose.yml file.
3.	Start the containers for each service in the application. The containers are started in the order they are defined in the docker-compose.yml file.
4.	Attach the terminal to the logs of all the containers, so you can see their output in real-time.
By default, the docker-compose up command runs in the foreground, so you can see the logs from all containers in the terminal. If you want to run the application in the background, you can use the -d or --detach option:
