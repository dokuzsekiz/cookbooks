# Rabbit MQ

## Installation

### Ubuntu

```bash
sudo apt-get install software-properties-common
sudo add-apt-repository "deb http://www.rabbitmq.com/debian/ testing main"
wget http://www.rabbitmq.com/rabbitmq-signing-key-public.asc
sudo apt-key add rabbitmq-signing-key-public.asc
sudo apt-get update
sudo apt-get install -q -y screen htop vim curl wget rabbitmq-server
ulimit -n 1024
sudo service rabbitmq-server stop
sudo rabbitmq-plugins enable rabbitmq_management
sudo service rabbitmq-server start
sudo rabbitmq-plugins list
```

Note:

* Managing the Broker `rabbitmqctl stop` and `rabbitmqctl status`
* Log files are at `/var/log/rabbitmq`

## Configuration

### Unix

```bash
touch /etc/rabbitmq/rabbitmq.config
touch /etc/rabbitmq/rabbitmq-env.conf
```

* https://www.rabbitmq.com/man/rabbitmq-env.conf.5.man.html

### User management

```bash
sudo rabbitmqctl delete_user guest
add_user deployer_user new_password_change_it
set_user_tags deployer_user administrator
```

* https://www.rabbitmq.com/man/rabbitmqctl.1.man.html#User management

### Access Controll

```bash
rabbitmqctl add_vhost vhostname
rabbitmqctl set_permissions -p vhostname username ".*" ".*" ".*"
```

* https://www.rabbitmq.com/man/rabbitmqctl.1.man.html#Access control
