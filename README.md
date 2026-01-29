# Microservice Deployment Using Virtual Machines

## Overview
This project demonstrates the deployment of a simple microservice-based application across two virtual machines. The setup was implemented on a MacBook (Apple Silicon) using UTM to create and manage virtual machines.

## Environment
- Host OS: macOS (Apple Silicon M1)
- Virtualization Tool: UTM
- Guest OS: Ubuntu Server 22.04 (ARM64)
- Number of VMs: 2

## Architecture
- VM-1: Backend microservice implemented using Python Flask
- VM-2: Client VM used to access the backend service
- Network Mode: Shared Network (NAT)

Refer to `architecture-diagram.png` for the architecture diagram.

## Backend Service
The backend microservice exposes the following REST endpoints:
- `/` : Returns a greeting message
- `/health` : Returns service health status

The service runs on port 5000 and listens on all network interfaces.

## How to Run

### On VM-1 (Backend)
```bash
python3 app.py

### On VM-2 (Client)
curl http://192.168.64.3:5000
curl http://192.168.64.3:5000/health

##Outcome
Successful communication between the two virtual machines confirms correct network configuration and microservice deployment.

backend/app.py
