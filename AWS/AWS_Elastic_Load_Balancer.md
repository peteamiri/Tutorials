# Elastic Load Balancers

* Load balancer virtual machine that route the payload to balance the workload.
* 3 types 
	* **Application Load-balancers** (NEW) 
		* best for HTTPS/HTTP load babancing, 
		* operates at Layer 7 of OSI
		* They are inteligent with **advance request routing**, sends a specific request to specific server
	* **Network Load-balancers** (NEW)
		* load balance TCP trafic with **extream performance**, Million of request per second with low latency
		* Operate at Layer 4 of OSI model (connection layer)
	* **Classic Load-balancers** (Legacy **ELB**)
		* Elastic load balancers, legacy load balancers
		* Load balance HTTP/HTTPS at layer 7 or Layer 4 TCP
		* It will have sticky sessions (Layer 7)
		* Associated with Error 504 Error **(gateway timeout)**
* X-Forwarded-For Header
	* the EC2 will not see the Internet IP address it will see the Internal IP address
	* You can X-Forwarded-FOR header to have External IP Address  

## Create healthcheck.html  for heatbeat 

* When instance failed the healthcheck it will not send payload to it. 
* You don't get public IP address to load-balance, you must use the DNS name always 