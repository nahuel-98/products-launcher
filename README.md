# Products launcher

The Products Launcher repository serves as the central hub for managing the various microservices that make up the product ecosystem. Its primary purpose is to streamline the process of launching and coordinating these microservices, ensuring they work together seamlessly. It uses Docker Compose to build and run the microservices in containers in a development environment. By leveraging Git submodules, it keeps track of the different microservices repositories, allowing for easy updates and maintenance.

## Key components

* **API Gateway:** Acts as a single entry point for clients. Routes requests to the appropriate services via NATS.
* **NATS:** A messaging server that allows microservices to communicate asynchronously. It acts as a message bus, where services can publish and subscribe to events.

* **Docker Network:** All microservices are located within a Docker network, making it easy to communicate with each other.
* **Stripe Webhook:** Stripe sends notifications to our system via a webhook, allowing our system to react to events such as successful or failed payments.

* **Microservices:**
* **Payments:** Handles payment processing. Integrates with Stripe to manage transactions.
* **Auth:** Handles user authentication.
* **Products:** Manages product information.
* **Orders:** Handles order creation and management, as well as order-related details.


## Architecture

![Image](https://github.com/user-attachments/assets/04a65ee4-d813-4c3c-9136-6914679a1aaf)

## Start the whole microservices - Development environment
1. Clone the repository.
2. Create a .env based on the .env.template.
3. Run the command `git submodule update --init --recursive`
4. Run the command `docker compose up --build`