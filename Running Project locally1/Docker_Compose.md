
**Phase 2: Multi-Container Networking with Docker Compose**

When an enterprise application has 10+ services (frontend, backend, databases, telemetry), running manual docker run commands for each one is impossible.

This is where Docker Compose comes in.

Look at docker-compose.yml in your project. It acts as an orchestrator for local development:


<img width="1377" height="132" alt="image" src="https://github.com/user-attachments/assets/71f4d26f-ce35-46bb-b4e4-f78238d7e66a" />


**The Secret: Docker Service Discovery (DNS)**

Inside Docker Compose:

Containers don't use IP addresses like 192.168.1.5 or 127.0.0.1.
Docker provides an internal DNS server. A service can reach the OpenTelemetry collector simply by typing http://otel-collector:4317.
Docker resolves otel-collector directly to the correct container IP automatically!





