Shape Framework Quick Start
======
Paolo Lulli 2012 - paolo@lulli.net

Make sure the executable shape is in the path:

	alias shape="path/to/the/script/shape"

and then begin using it. Let's create a new project:

	paolo@/tmp$ shape init MyProject
	
At the prompt, enter the IP address or hostname for the web machine

	Remote machine:
	192.168.1.135
the user on that machine

	Remote user:
	webdev
the web directory on the host

	Remote frontend dir:
	/home/webdev/public_html

and a directory on the host that is preferably outside of the webserver published resources

	Remote backend dir:
	/home/webdev/MyProject

then you can see that shape created a configuration for you:

	paolo@/tmp$ cd MyProject/
	paolo@/tmp/MyProject$ ls -la
	total 16
	drwxr-xr-x   5 paolo  wheel  170 12 Lug 16:57 .
	drwxrwxrwt  20 root   wheel  680 12 Lug 16:56 ..
	-rw-r--r--   1 paolo  wheel  197 12 Lug 16:57 .shape.config
	-rw-r--r--   1 paolo  wheel  494 12 Lug 16:57 server.cfg
	drwxr-xr-x   2 paolo  wheel   68 12 Lug 16:56 web
	paolo@/tmp/MyProject$ cat .shape.config 
	project_name=MyProject
	remote_host=192.168.1.135
	remote_user=webdev
	remote_frontend_dir=/home/webdev/public_html
	remote_backend_dir=/home/webdev/MyProject
	remote_gateway_dir=/home/webdev/MyProject

To distribute the shape framework over the remote web machine, issue the command:

	paolo@/tmp/MyProject$ shape dist

Your website code goes into the web directory; you can publish it by issuing:

	paolo@/tmp/MyProject$ shape sync

that will sync your local development dir with the one on the server
