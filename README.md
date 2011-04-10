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

### Configuration file sample

/etc/passenger/blog.yml

    rvm: ruby-1.9.2@example
    cwd: /var/apps/blog/current
    user: deploy
    port: 8080
    environment: production
    max-pool-size: 4
    min-instances: 1
    pid-file: /var/apps/blog/current/tmp/pids/passenger.pid
    log-file: /var/apps/blog/current/log/passenger.log

Usage
-----

### Start all applications

    sudo /etc/init.d/passenger start

### Stop all applications

    sudo /etc/init.d/passenger stop

### Restart all applications

    sudo /etc/init.d/passenger restart

### Reload all applications

    sudo /etc/init.d/passenger reload

### Get applications status

    sudo /etc/init.d/passenger status

### Start certain applications

    sudo /etc/init.d/passenger start blog forum

### Stop certain applications

    sudo /etc/init.d/passenger stop blog forum

### Restart certain applications

    sudo /etc/init.d/passenger restart blog forum

### Reload certain applications

    sudo /etc/init.d/passenger restart blog forum

### Get status for certain applications

    sudo /etc/init.d/passenger status blog forum

### Enable application

    sudo /etc/init.d/passenger enable blog

### Disable application

    sudo /etc/init.d/passenger disable blog


Notes
-----

* restart command stops and then starts passenger instances
* reload or upgrade command graceful replaces passenger workers

