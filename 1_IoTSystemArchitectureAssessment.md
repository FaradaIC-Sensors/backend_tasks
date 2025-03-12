# IoT System Architecture Assessment

## Background
Our IoT network consists of devices that transmit environmental sensor data 
packets in ALOHA mode to a central network server. 

The network server occasionally sends configuration packets (downlinks) back to devices. 

Devices can only receive downlinks during a brief window following their uplink transmission.

The network server maintains data in a MySQL database.

After processing, data is transferred to a business applications server
that presents information to clients through web and mobile applications. 

Both the network server and business applications are hosted on the same VPS.
The system prioritizes simplicity and is designed for 10,000 devices, 
each transmitting one data packet hourly with transmissions evenly distributed over time.

## Questions
Please sketch the architecture of your solutions with appropriate benchmarks. No code implementation is required.

### 1. Data Transfer Architecture
Design a mechanism to transfer new data between the network server database and the business application server.

It's acceptable to trade some processing delay for improved robustness and simplicity.

In your solution:
- Outline the architectural approach
- Provide estimated throughput metrics
- Discuss potential bottlenecks
- Explain how your solution would scale if device count increases to 100,000

### 2. Downlink Management System
Design a downlink packet functionality for the network server.

The client should be able to schedule downlink packets from the web-app and phone app
via the business application and these packets should be transferred to the devices via the network server.

Include the API design that would allow the business application to communicate with the network server for downlink scheduling. 
