**Vanderbilt University**

**2020 Distributed Systems Principles(CS6381) Assignment2 : Pub/Sub Model Implementation using ZeroMQ+Zookeeper**

## System Diagram
![SystemDiagram](SystemDiagramV3.png)

## How to Execute
**0. Prerequirement**
 - Mysql Database
  - user information : ID - 'lhh@localhost', PW - '1234'
  - Database Name : pubsub
  - Table Information
     1. publisher
        -- create table publisher(topic varchar(100), socket_id varchar(100));
        
     2. subscriber
        -- create table subscriber(topic varchar(100), socket_id varchar(100));
  
     3. brokerrecord
        -- create table brokerrecord(publisher_port varchar(10), broker_address varchar(100), topic varchar(100), contents varchar(1000), start_time timestamp, elapsed_time FLOAT(20,10));

**1. Publisher to Subscribers using Broker (i.e. 3 Subscribers and 1 Publisher)**
* broker's IP address and Port number are required
 - $ python broker.py
 - $ python3 sub.py I 127.0.1.1 5559
 - $ python3 sub.py I 127.0.1.1 5559
 - $ python3 sub.py I 127.0.1.1 5559
 - $ python3 pub.py I 127.0.1.1 5559 Y

**2. Directly from Publisher to Subscribers (i.e. 3 Subscribers and 1 Publisher)**
* broker's IP address and Port number are required
 - $ python broker.py
 - $ python sub.py D 127.0.1.1 5559 N
 - $ python sub.py D 127.0.1.1 5559 N
 - $ python sub.py D 127.0.1.1 5559 N
 - $ python pub.py D 127.0.1.1 5559 N
 
 
 ## Testing Environment
  - Minimal 3 client Topology
  ![Topology](Topology.png)
