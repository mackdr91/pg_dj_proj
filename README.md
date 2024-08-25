## Postgres Service:
	•	Image: Using the official PostgreSQL Docker image.
	•	Environment: Sets the user, password, and database name.
	•	Volumes: Persists the PostgreSQL data on your local machine.
	•	Networks: Connects to a custom network for inter-service communication.
## Django Service:
	•	Image: Uses the official Django image. (If you have a custom Dockerfile for Django, replace this with build: . and ensure your Dockerfile is in the project root.)
	•	Command: Runs Django’s development server.
	•	Volumes: Mounts your project directory to the container, enabling live code updates.
	•	Ports: Exposes port 8000 to access Django in the browser.
	•	Environment: Passes PostgreSQL connection settings to Django.
	•	Depends_on: Ensures PostgreSQL starts before Django.
	•	Networks: Connects to the same network as PostgreSQL.
## pgAdmin Service:
	•	Image: Uses the official pgAdmin image.
	•	Environment: Configures the default admin credentials for pgAdmin.
	•	Ports: Maps port 5050 on the host to port 80 on the container.
	•	Depends_on: Ensures PostgreSQL starts before pgAdmin.
	•	Networks: Connects to the same network as the other services.
