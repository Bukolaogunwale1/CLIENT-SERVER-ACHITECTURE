# CLIENT-SERVER-ACHITECTURE
## Implementing Client- Server architecture using MYSQL database system 
 
The client–server model is a distributed application structure that partitions tasks or workloads between the providers of a resource or service, called servers, and service requesters, called clients.

A server host runs one or more server programs, which share their resources with clients. A client usually does not share any of its resources, but it requests content or service from a server.

Clients, therefore, initiate communication sessions with servers, which await incoming requests. Examples of computer applications that use the client–server model are email, network printing, and the World Wide Web.

# IMPLEMENTING CLIENT-SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS)

To demonstrate basic client-server using MySQL RDBMS

**To create and configure two linux based Virtual servers(EC2 instances on AWS)**

Name the two servers: 

- Server A name - `mysql server`
- Server B name - `mysql client`

<img width="960" alt="CREATION OF MYSQL FOR SERVER AND CLIENT" src="https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/8ef43d25-bb97-4700-be06-54e99e9c587f">

- Connect to the `MySQL-Server` and Install `MySQL software`

  - Run `sudo apt install mysql-server` to install Mysql software .

<img width="735" alt="SUDO APT MSQL SERVER" src="https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/b347082d-44f1-4b97-a534-7ce927ac1796">

- To install Mysql for the client server

 - Run `sudo apt install mysql-client`

<img width="631" alt="SUDO APT INSTALL MYSQL CLIENT" src="https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/229896d6-3f9e-4415-b293-7e999d9245ae">

By default both EC2 virtual servers are located in the same local virtual network. so they can communicate with eachother using using local `IP address`

- To use `MySQL-server` local Ip address to connect from the client

  - Change the inboud rule to TCP to port 3306 and connect to Clients `Private Ip address`

<img width="586" alt="oyaa" src="https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/54387e15-fbb5-4529-a4ad-2d372ded4680">

To connect *Client* to *Server*, We need to configure `MySQL-Server` to allow connection from remote host.

![image](https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/161640bd-e79d-4b8e-ab68-b373416bbc45)

To Run connect the *client-mysql* to the *Server-mysql* without using  `SSH`

 - Run `sudo mysql` to log in to the MYSQL console and paste the code below.

 <img width="650" alt="create user on mysql server" src="https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/1f2a96f2-3dc0-41a4-b13c-0f594b679e03">

 Run the code below to create a user called `folake` and the user should be identified by a password `bukola` on the `MySQL-Server`

 ```
CREATE USER 'folake'@'%' IDENTIFIED BY 'bukola;
 ```
<img width="650" alt="create user on mysql server" src="https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/a5185795-dd1b-40f0-b4d4-1b0e6c233222">

- Then From the client server run `mysql -u folake -p -h 172.31.36.157`using the private Ip of the *Server

```
Show databases
```
<img width="648" alt="show databases" src="https://github.com/Bukolaogunwale1/CLIENT-SERVER-ACHITECTURE/assets/122865359/06aa25fd-c233-4216-935b-e7a779a22c77">




