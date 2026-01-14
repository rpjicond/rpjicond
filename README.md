<!-- Improved compatibility of back to top link: See: https://github.com/othneildrew/Best-README-Template/pull/73 -->

<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/rpjicond">
    <img src="https://cdn-icons-png.flaticon.com/512/9672/9672159.png" alt="Logo" width="80" height="80">
  </a>

<h3 align="center">IoT Zero Trust Security Platform</h3>

  <p align="center">
    An automated infrastructure project implementing Zero Trust architecture for IoT ecosystems, featuring mTLS, Network Segmentation, and PKI Automation.
    <br />
    <a href="https://github.com/rpjicond/iot-zero-trust-platform"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/rpjicond/iot-zero-trust-platform">View Demo</a>
    &middot;
    <a href="https://github.com/rpjicond/iot-zero-trust-platform/issues">Report Bug</a>
    &middot;
    <a href="https://github.com/rpjicond/iot-zero-trust-platform/issues">Request Feature</a>
  </p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#key-features">Key Features</a>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->

## About The Project

![Project Architecture Screen Shot](https://via.placeholder.com/800x400.png?text=Network+Topology+%26+Architecture+Diagram)

In the modern landscape of **Internet of Things (IoT)**, security cannot be an afterthought. Traditional perimeter-based security models fail when thousands of devices are distributed across edge networks.

This project, **IoT Zero Trust Security Platform**, is a robust infrastructure solution designed to secure device-to-cloud communication. It moves beyond simple VPNs to enforce a strict "Never Trust, Always Verify" policy.

**Why this project stands out:**
*   It bridges the gap between **Network Engineering** (segmentation, protocols) and **Software Development** (API, Automation).
*   It eliminates hardcoded credentials by using dynamic secrets and automated certificate rotation.
*   It provides real-time observability into network traffic and device health.

This repository serves as a practical implementation of **DevSecOps** principles applied to Network Engineering.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Built With

This project leverages a stack focused on **Networking, Automation, and IoT Protocols**:

*   [![Cisco][Cisco]][Cisco-url]
*   [![Linux][Linux]][Linux-url]
*   [![Python][Python]][Python-url]
*   [![Bash][Bash]][Bash-url]
*   [![Docker][Docker]][Docker-url]
*   [![Grafana][Grafana]][Grafana-url]
*   [![Wireshark][Wireshark]][Wireshark-url]
*   [![Mosquitto][Mosquitto]][Mosquitto-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- KEY FEATURES -->
## Key Features

*   **Network Automation:** Bash and Python scripts to automate the lifecycle of X.509 certificates (PKI) and device enrollment.
*   **Secure Protocols:** Implementation of **MQTT over TLS (mTLS)** ensuring end-to-end encryption.
*   **Infrastructure as Code:** Docker Compose orchestration for rapid deployment of the backend stack (HashiCorp Vault, Database, Broker).
*   **Observability:** Real-time dashboards using Grafana/InfluxDB to monitor network latency and packet loss.
*   **Identity Management:** Centralized secrets management preventing unauthorized access.

<!-- GETTING STARTED -->

## Getting Started

To get a local copy up and running for testing the network simulation, follow these steps.

### Prerequisites

You need a Linux environment (Ubuntu/Debian recommended) or WSL2 on Windows.

*   **Docker & Compose**
    ```sh
    sudo apt-get install docker.io docker-compose
    ```
*   **OpenSSL** (For local certificate generation)
    ```sh
    sudo apt-get install openssl
    ```
*   **Python 3.x**
    ```sh
    sudo apt-get install python3-pip
    ```

### Installation

1.  Clone the repository
    ```sh
    git clone https://github.com/rpjicond/iot-zero-trust-platform.git
    ```
2.  Navigate to the project directory
    ```sh
    cd iot-zero-trust-platform
    ```
3.  Run the PKI Automation script to generate root and intermediate certificates
    ```sh
    chmod +x scripts/generate-certs.sh
    ./scripts/generate-certs.sh
    ```
4.  Start the Infrastructure containers
    ```sh
    docker-compose up -d
    ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- USAGE EXAMPLES -->

## Usage

### 1. Network Simulation
Use the provided python scripts to simulate IoT devices sending telemetry data over a secure channel.

```sh
python3 src/device_simulator.py --device-id ESP32_01 --cert ./certs/device.crt
