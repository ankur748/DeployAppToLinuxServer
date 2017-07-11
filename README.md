# DeployAppToLinuxServer

- Item Catalog App is hosted on LightSail AWS VM with IP as 35.154.129.24
- Flask Application is deployed as a WSGI app with Apache 2 on Port 80
- Application can be accessed directly at http://35.154.129.24/
- Softwares used for deployment are
1) Pip for Python Package Installation and Management
2) Flask as Python Web Application Framework
3) SqlAlchemy as Python ORM Library for the Application
4) FuncTools for Python decorator functions
5) oauth2client and httplib2 for OAuth in Python
6) json to parse secret json files in Python
- Used Postgres SQL as the Backend database

Configurations Made

- Updated and Upgraded all the installed packages

- Change the sshd config to change default port of 22 to 2200
- Denied all incoming connections by default and allowed all outgoing connetions on ufw firewall
- Allowed only three ports for incoming connection which are

a) 2200 SSH port
b) 80 HTTP port
c) 123 NTP port

- Created new user grader with the credentials and added him to sudoers list
- Created a SSH key pair which will be allowed to be logged in for grader user
- Disabled password logins for users on machine in ssh config

- Installed apache2 for http server
- Installed mod_wsgi application to run python applications through apache server
- Installed Postgres SQL server
- Created a new user on Postgres and a database which he is allowed to do operations on
- Cloned the git library https://github.com/ankur748/ItemCatalog from my Nanodegree Project
- Integrated the connection string in database_setup and database_helper files with respect to user and database created before
- Integrated the flask app into apache server
- Changed the redirect URIs of Facebook to point to new instance
- Changed permissions of .git folder to make it inaccessible from http server