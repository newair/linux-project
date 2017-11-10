# Linux Project
## Deployment of Item catalog project in Amazon Lightsail
## Done by Amila Ishara Ranatunga for Udacity fullstack web developer Nanodegree program

## Basic details 

* Ip Address: http://54.255.179.30
* SSH Port: 2200
* Complete URL: http://54.255.179.30

## Summary of the software installed

* Finger
* Apache/2.4.18
* libapache2-mod-wsgi
* bleach 2.0.0
* certifi  2017.7.27.1
* chardet  3.0.4
* click  6.7
* Flask  0.12.2
* Flask-HTTPAuth  3.2.3
* Flask-SQLAlchemy  2.2
* gunicorn  19.7.1
* html5lib  0.999999999
* httplib2  0.10.3
* idna  2.6
* itsdangerous  0.24
* Jinja2  2.9.6
* MarkupSafe  1.0
* oauth2client  4.1.2
* packaging  16.8
* passlib  1.7.1
* psycopg2  2.7.3.1
* pyasn1  0.3.3
* pyasn1-modules  0.1.1
* pyparsing  2.2.0
* redis  2.10.6
* requests  2.18.4
* rsa  3.4.2
* six  1.10.0
* SQLAlchemy  1.1.14
* urllib3  1.22
* webencodings  0.5.1
* Werkzeug  0.12.2
* git

Changes Made

Updating the software package of the server
sudo apt-get update

Enable port 2200
sudo vi /etc/ssh/sshd_config 
and change ssh port to 2200

Allow the port from firewall
sudo ufw allow 2200/tcp

Disallow incomming requests
sudo ufw default deny incoming

Allow outgoing requests
sudo ufw default allow outgoing

Create a user Grader and grant sudo access
sudo cp /etc/sudoers.d/90-cloud-init-users /etc/sudoers.d/grader

Creating Key pair for grader User and save public key
mkdir .ssh
touch .ssh/authorized_keys
nano .ssh/authorized_keys
 chmod 700 .ssh
chmod 644 .ssh/authorized_keys

Change time zone of the server
tzselect

Install Apache 2
sudo apt-get install apache2

Install Apache 2 WSGI
sudo apt-get install libapache2-mod-wsgi

Install git and checkout Item-category project
sudo apt-get install git

Creating a virtual host file 
/etc/apache2/sites-available/market-item-category.conf

Adding the Application specific details to the file

Installing pythin pip (package management system)
pip install -U pip setuptools

Install all the dependencies with pip
pip install -r requirements.txt

created the market-item-category.wsgi and inserted the relevant imports

changed the code to read the files from the app-root path.

used scoped_session(sessionmaker(bind=engine)) in order to prevent 
 ProgrammingError: SQLite objects created in a thread can only be used in that same thread


list of third-party resources

https://httpd.apache.org/docs/
https://aws.amazon.com/ docs
http://flask.pocoo.org/docs/0.12/deploying/mod_wsgi/
https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
https://packaging.python.org/tutorials/installing-packages/
https://pip.pypa.io/en/stable/user_guide/
https://stackoverflow.com/

