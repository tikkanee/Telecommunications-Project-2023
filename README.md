# Telecommunications Project (Year 2)

***Created by Aapo Tikkanen and Pete Vuorela***

## Project Overview:

This project focuses on creating a client for Nordic nRF5340, a sensor device, to measure data (accelerometer readings) and transmit it wirelessly to an IoT router (Raspberry Pi). The Raspberry Pi acts as a gateway, forwarding the data to Oamk's MySQL server. The stored data in the database is accessible through both a TCP socket interface and a simple HTTP API.

### Project Features

- Nordic Client: Develop a client application to interface with the Nordic nRF5340 sensor device, collecting sensor data and preparing it for transmission.

- Wireless Transmission: Implement a reliable wireless communication mechanism to transmit the collected sensor data from Nordic to the Raspberry Pi IoT router.

- Raspberry Pi Gateway: Set up the Raspberry Pi to receive data from Thingy and forward it to OUAS's MySQL server. Ensure data integrity and security during the transmission process.

- Database Integration: Design the MySQL database schema to store sensor data. Implement a TCP socket interface and a straightforward HTTP API for data retrieval.

- Machine Learning Integration: Develop a custom program to fetch data from the HTTP API, processing it for machine learning purposes on a local machine.
  
![1](https://github.com/user-attachments/assets/8dd420c4-b620-421c-9c01-2296d7079738 "Diagram illustrating data transfer connections and various components of the project ")


## Nordic BLE

  
  ### BLE Data Transmission to Phone:
  
  Implemented a program that transmits data over BLE to a connected mobile device.
  
  ### Periodic Integer Data Transmission:
  
  Developed a program that periodically sends integer data over the BLE connection. If the nfrConnect app is installed on the phone, it can subscribe to and receive this data.
  
  ### Button  Activation:
  
  Enabled Button on the nrf5340dk platform. When pressed, Button to toggle the direction variable's value between 0, 1, 2, 3, 4, 5, 0, 1, ... with each button press.
  
  ### BLE Transmission of Sensor Information:
  
  Modified the program to send direction information, as well as x, y, and z acceleration values over the BLE connection when someone subscribes to sensor 

![2](https://github.com/user-attachments/assets/76d52e8e-1bcb-4dc1-b680-786869cf40d5 "Nordic nRf5340 and accelometer")



## Data to SQL


  ### Raspberry Pi Setup:

  Successfully installed and connected Raspberry Pi to the Telecommunication Lab's Ethernet network.
    
  ### Bluetooth Data Reception with Python:

  Crafted a Python program for Raspberry Pi that adeptly receives data from the Nordic platform via Bluetooth. This data is then intelligently written to our MySQL server.
   
  ### Dynamic PHP Script for Linux Server

  Developed a dynamic PHP script on our Linux server residing in /var/www/html. This script effortlessly fetches and displays measurement data sent from Raspberry Pi, conveniently stored in the Telecommunication Lab's MySQL database.
    
  ### Python TCP Client for Laptop:

  Created a Python TCP client program for our laptops. This sophisticated program efficiently retrieves, processes, and stores data from the server (utilizing HTTP transfer) into CSV files on our laptops. 
    
  ### Direct Database Query with Python:

  Introduced a new Python script capable of fetching data directly from the database using the MySQL interface.

![3](https://github.com/user-attachments/assets/d1fc7b37-5dd9-491a-a959-8f200033a9a2 "Raspberry Pi")



## K-means


  ### Read Accelerometer Data from the Database:
  
  Successfully implemented a Python script to read accelerometer data from the MySQL database.
  
  ### Data Transformation for Algorithm:
  
  Skillfully transformed the accelerometer data into the required format for the algorithm.
  
  ### Algorithm Training:
  
  Implemented an algorithm that dynamically learns from the data until there are no further changes in the centroids after subsequent training sessions (e.g., the count value for each centroid remains constant).
  
  ### Persistent Storage of Trained Centroids:
  
  Stored the trained centroids in MySQL for easy retrieval and reference.

![4](https://github.com/user-attachments/assets/43ff12c9-02b2-421f-8e4f-d81650bb2f71 "Pictures show how centroids move towards datapoint groups after one iteration")
![5](https://github.com/user-attachments/assets/caeec937-4a8e-4deb-867d-98fcb98f2102 "Pictures show how centroids move towards datapoint groups after one iteration")



## Confusion Matrix


  ### Centroid Inclusion with keskipisteet.h:

  Introduced a keskipisteet.h file for easy inclusion in the C program. This file contains the six centroids trained in Python.

  ### Confusion Matrix Implementation:

  Implemented missing subroutines in the confusion.c file. These subroutines are crucial for conducting measurements and evaluating the performance of the K-means classification algorithm.

  ### Measurements and Analysis:

  Conducted measurements using the accelerometer utilized earlier during the data collection phase. The distances from the 3D point to the six centroids are calculated and utilized in the K-means algorithm.

  ### Confusion Matrix Results:

  The result of the project is a confusion matrix that showcases the effectiveness of the K-means classification algorithm

![6](https://github.com/user-attachments/assets/b5831c7e-e325-44ee-9872-fd23dd6fbd69 "Compeleted confusion matrix")



## Additional tasks

  ### Firewall Script (Linux)

  We made a script to configure Netfilter firewall on a Linux server. The script allows testing of the firewall's effectiveness by keeping TCP ports 80 and 22 open for specific destinations while managing ICMP traffic. The functional script is available in this repository for reference and implementation on other servers.

  ### Apache + PHP (Linux)

  We set up a Apache web server and PHP on a Linux server. It includes PHP scripts for basic date display and fetching data from a MySQL database. The repository also contains instructions to capture and analyze network traffic between the server and browser using tcpdump and Wireshark. The goal is to analyze page loading times and HTTP response headers both through tcpdump and browser debugging tools.
  
![7](https://github.com/user-attachments/assets/76ba2ad1-aa42-49e4-a2ec-944fc2b26b30 "Connected to our Linux server")


  ### Thunder Client

  We tested API using Thunder Client for Ilmatieteenlaitos (weather data) and Oulun Liikenne (parking garage reservations). The repository includes Thunder Client scripts for HTTP GET and POST requests, along with tests ensuring correct responses, content validation, and response length constraints. It provides an insightful example of API testing with Thunder Client.

  ### TCP-client

  We made a Python script demonstrating the usage of a TCP socket client to interact with the Tietoliikennelabra server. The script sends a group ID, retrieves data from the server, and provides the option to save the received data to a file. The repository serves as a practical example of socket communication with a server and data handling in Python.
