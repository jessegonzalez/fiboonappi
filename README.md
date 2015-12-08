Fibonappi - Generate n integers of the Fibonacci sequence.
=========================================================

Install
-------
Use pyenv, virtualenv, or virtualenv wrapper to create a virtualenv using python 2.7.x.

For example:
```
pyenv virtualenv 2.7.6 fibonappi
pyenv actictivate fibonappi
```

Run Tests
---------
```
python setup.py test
```


Run Application - Test
----------------------
```
python fibonappi.py
```

Now navigate to http://localhost:5000 for some Swagger!

Run Application - Production
----------------------------
```
apt-get update
apt-get install git nginx python-dev python-virtualenv supervisor
cd /opt
git clone https://github.com/jessegonzalez/fibonappi.git
virtualenv /opt/fibonappi/venv
source /opt/fibonappi/venv/bin/activate
mkdir /var/run/fibonappi
chmod 0777 /var/run/fibonappi
mkdir /var/log/fibonappi
chown www-data:www-data /var/run/fibonappi
cp /opt/fibonappi/fibonappi.conf /etc/supervisor/conf.d/
supervisorctl reread && supervisorctl reload
rm /etc/nginx/sites-enabled/default
cp /opt/fibonappi/fibonappi-nginx /etc/nginx/sites-available/fibonappi
ln -s /etc/nginx/sites-available/fibonappi /etc/nginx/sites-enabled/fibonappi
service nginx restart
```

