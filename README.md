## How to setup Redis master instance (Ubuntu)

	mkdir redis-setup
	cd redis-setup
	wget https://raw2.github.com/eugene-kartsev/redis-setup/master/redis-master-setup.sh
	
Edit 'redis-master-setup.sh' file, change the following properties (if you need to):

	REDIS_VER=2.8.3
	UPDATE_LINUX_PACKAGES=false
	REDIS_INSTANCE_NAME=redis-server
	REDIS_INSTANCE_PORT=6379	

Run script:

	sudo sh redis-master-setup.sh

After the execution you'll se something like:

	*****************************************
	 Installation Complete!
	
	 Configure redis-server in /etc/redis-server/redis.conf
	
	 WARNING: Service isn't started by default.
	 Use the following command to manipulate [redis-server] Redis service:
	 sudo /etc/init.d/redis-server [start|stop|restart]

Run the following command to start Redis service:

	sudo /etc/init.d/redis-server start

Check that the service has been started:

	ps aux | grep redis

The following line should appear:

	redis ... /usr/local/bin/redis-server *:6379
