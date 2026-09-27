# API-Gateway# Distributed Rate-Limiting API Gateway

> An enterprise-grade reverse proxy and API Gateway designed to route incoming traffic, manage load, and protect downstream microservices from API abuse and DDoS attacks using in-memory caching.

## 🚀 System Architecture & Features

This gateway intercepts incoming HTTP requests, validates the client's IP address against a strict quota stored in Redis, and either routes the traffic to the upstream service or immediately drops the request to preserve server resources.

*   **Algorithmic Rate Limiting:** Implements a Sliding Window / Fixed Window counter utilizing Redis to track request quotas in real-time.
*   **High Throughput:** Designed to handle 800+ concurrent requests per second with sub-15ms latency overhead.
*   **Traffic Shaping:** Automatically returns `429 Too Many Requests` status codes and specific error messages when thresholds are breached.
*   **Decoupled Infrastructure:** Containerized with Docker for rapid, environment-agnostic deployment.

## 🛠 Tech Stack

*   **Runtime:** Node.js, Express.js
*   **In-Memory Storage:** Redis (for distributed rate-limit tracking)
*   **Routing:** `http-proxy-middleware`
*   **Containerization:** Docker, Docker Compose
*   **Load Testing:** Artillery / Apache JMeter

## ⚙️ Local Setup & Installation

### Prerequisites
Ensure you have [Node.js](https://nodejs.org/) and [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed on your local machine.

### 1. Clone the Repository
```bash
git clone https://github.com/Pixi-Me/API-Gateway.git
