Passenger initscript
====================

Goals
-----

* bash script
* muliple passenger standalone instances
* rvm support
* yaml application configuration

Installation
------------

    cd /etc/init.d
    sudo wget https://github.com/railsware/passenger-initscript/raw/master/passenger
    sudo chmod +x passenger

    sudo /etc/init.d/passenger setup

    sudo cp /etc/passenger.d/example.yml.disabled /etc/passenger.d/app1.yml
    sudo cp /etc/passenger.d/example.yml.disabled /etc/passenger.d/app2.yml
    ...

Edit configurations according to your needs.

Usage
-----

### Start all applications

    sudo /etc/init.d/passenger start

### Stop all applications

    sudo /etc/init.d/passenger stop

### Get applications status

    sudo /etc/init.d/passenger status

### Start certain applications

    sudo /etc/init.d/passenger start blog forum

### Stop certain applications

    sudo /etc/init.d/passenger stop blog forum

### Get status for certain applications

    sudo /etc/init.d/passenger status blog forum

### Enable application

    sudo /etc/init.d/passenger enable blog

### Disable application

    sudo /etc/init.d/passenger disable blog
