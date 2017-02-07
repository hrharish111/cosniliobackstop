#Initial Setup for Consilio's Backstop

>This setup is based with Ubuntu Operating system

####Basic requirement:
* Python 2.7
* ElasticSearch
* Vowpal Wrabbit

### Installation:

- Python is installed by default in ubuntu
- Elastic search :
	- first you need to update your os :
		- ```$sudo apt-get update```
	- Then you need to have java installed in you machine :
		-	```$sudo apt-get install openjdk-7-jre ```
	-	To verify java version
		- ``` $java -version ```
	- Download the elastic search latest version using terminal
		- ``` $wget https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-1.7.2.deb  ```
		
- Vowpal wrabbit :
	- you have to clone from git
		-	```git clone git://github.com/JohnLangford/vowpal_wabbit.git```
	- Now we compile :
		- ``` cd vowpal_wrabbit ```
			- ``` ./autogen.sh ```
			- ``` ./configure ```
			-	``` make ```
	- If it fails, you most likely need to install the boost program options headers and library.
		- Boost installation on Debian-based (Debian, Ubuntu, Mint etc.) Linux distributions:
			- ```sudo apt-get install libboost-program-options-dev libboost-python-dev```
			
			- ``` make vw ```
	- for more help follow the below link :
		- [vowpal wrabbit](https://github.com/JohnLangford/vowpal_wabbit/wiki/Tutorial)

####Project setup :
1. Create virtualenvironment  to start your project, if you have not installed virtualenvironment install with
	-  `pip istall virtualenv`  or `sudo apt-get install virtualenv`		
	- To create virtual env from your terminal :
		- ```$virtualenv environmentname```
	- To activate virtualenv :
		-	``` $source environmentname/bin/activate ```
2. Installing the packages
	- Installing packages using requirement.txt is suggested
		- ```pip install -r requirement.txt ```
		- or
		- Install each packages indivisually :
			- ``` pip install Beaker==1.8.1 ```
			- ``` pip install argparse==1.2.1 ```
			- ```pip install boto==2.45.0```
			- ```pip install funcsigs==1.0.2```
			- ```pip install gevent==1.2.1```
			- ```pip install greenlet==0.4.12```
			- ```pip install psutil==5.1.2```
			- ```pip install pycrypto==2.6.1```
			- ```pip install pyes==0.99.6```
			- ```pip install six==1.10.0```
			- ```pip install urllib3==1.20```
			- ```pip install wsgiref==0.1.2```
		
		- if any error persist follow respective documents
	3. Pull the front end code outside the project :
		- [web](https://github.consilio.com/bmerrell/web.git)
		
	### Steps to run the code
	- first you need to create the user
		- ``` python set_user.py username ```
			- then it asks for password and confirm the password
	
	- To run the server 		
		- ``` python web_service.py 'portnumber'  ```
		
	- inorder to upload the zip folder inside the project you need to run zip_handler
		- ``` python zip_handler_run.py ```
	- inorder to check status and stats inside the project you need to run stats_run
		- ``` python stats_run.py```
