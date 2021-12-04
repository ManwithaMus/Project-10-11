# Project-10-11
# Honeypot Assignment

**Time spent:** **5** hours spent in total

**Objective:** Create a honeynet using MHN-Admin. Present your findings as if you were requested to give a brief report of the current state of Internet security. Assume that your audience is a current employer who is questioning why the company should allocate anymore resources to the IT security team.

### MHN-Admin Deployment 

**Summary:** When deploying the MHN-Admin server, I made use of Google Cloud Platform(GCP) in order to configure and manage/setup the server.

(It's worth noting that the gif doesn't show the whole process as the MHN installation process is long and had already been done before, which can be seen from the files inside the folders on the ssh server)
![Animation1](https://user-images.githubusercontent.com/44510729/144704577-e4013a27-c358-4e32-9ea7-ca29f4fd9e08.gif)

### Dionaea Honeypot Deployment 

**Summary:** I then made another server using GCP and configured it to act as the honeypot. I then downloaded the Dionaea honeypot software which would make use of the purposefully exposed ports on the server to collect and trap incoming potentially harmful traffic going to those ports, things like attack payloads and malware.  

(It's worth noting that the gif doesn't show the whole process as the Dionaea honeypot installation process is long and had already been done before, which can be seen from the files inside the folders on the ssh server)
![Animation2](https://user-images.githubusercontent.com/44510729/144704765-03425f14-22ae-40e4-8aca-bd1081fce2ff.gif)


### Database Backup  

**Summary:** The RDBMS that the MHN-Admin server uses records the traffic to the ports which the Dionaea honeypot had picked up. The JSON file that I had exported contains data like the IP address of the source of the attack, the date in which the attack was performed, and the port which had been attacked. 

![Animation3](https://user-images.githubusercontent.com/44510729/144704863-4a736ff5-3327-4d2b-8afa-40d293a1e098.gif)

### Deploying Additional Honeypot(s) 

**Summary:** While I had chose not to deploy additional honeypots, I certainly had the option to as the MHN-Admin server supports a variety of differnet honeypots such as Glastopf and Amun.

![Animation4](https://user-images.githubusercontent.com/44510729/144704896-25dcf5fa-bf71-4789-b41f-49c8a56a6345.gif)

#### X Honeypot

**Summary:** Using a variety of honeypots would diversify the range of attacks that could be captured, allowing for a more thorough investigation of possible vulnerabilities within a system.

![Animation6](https://user-images.githubusercontent.com/44510729/144705139-2471b545-6ee0-4753-ba22-82c9ba28e687.gif)

### Malware Capture and Identification 

**Summary:** While I could not find strong evidence of captured malware, I had identified other possible exploits that could have attacked the honeypot such as a mssqld attack which could been identified by using the mssqld protocol.

![Animation5](https://user-images.githubusercontent.com/44510729/144705040-dae86f87-93f4-4b0f-a385-8c62873c2bd1.gif)

## Notes

While attempting to complete this assignment, I ran into a few configuration issues with the GCP terminal. One of the issues was that when starting up the GCP terminal, it would always fail to find the python interpreter which I had installed in a standard location on my computer. since GCP is supposed to look for a python interpreter on startup, it was unusual for it to not be able to find it. I fixed this issue however by providing the absolute path to the python interpreter to GCP. Another issue was with setting up the MHN-Admin server. When I would ssh into the server using Putty, every time I would attempt to install the needed programs, the putty session would expire, kicking me out of the ssh and aborting/breaking the installation. I was able to circumvent this however by changing Putty's settings so that it would send null packets at a regular interval in order to keep the session active.

![PuttyConfig](https://user-images.githubusercontent.com/44510729/144704199-33e082ba-93bc-462c-987e-2b6cde885caf.GIF)
