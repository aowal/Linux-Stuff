# Run jupyter notebook in remote server using SSH tunneling


### In remote host, open the terminal and type:

 `jupyter notebook --no-browser --port=8889`
  
### In your local computer, open terminal, then type:
  
  `ssh -N -f -L localhost:8888:localhost:8889 username@your_remote_host_ip`
  
### Now open google chrome and type:
  
  `localhost:8888`

# Setup jupyter to run in remote server

### Login as a non-root user and check in your home directory if a ".jupyter" folder exists. This folder holds the notebook configuration file "jupyter_notebook_config.py". If it does not exist, create it with the following command:
	
 `jupyter notebook --generate-config`

### To secure the notebook with password first prepare a hashed password using the function in python:
	
 ```from IPython.lib import passwd'
 password = passwd("your_password")
 password
 'sha1:9e59c5ba9186:cecf9600b48b50f076c4481f0ce522d9f091cc90'```

### Then to access with https create a ssl certificate in ~/.jupyter folder valid for 365 days with both the key and certificate data written to the same file:

 `openssl req -x509 -nodes -days 365 -newkey rsa:1024 -keyout mycert.pem -out mycert.pem`

 ### Now edit the notebook config file, jupyter_notebook_config.py. By default, the notebook config file has all fields commented out. Now uncomment and edit jupyter_notebook_config.py as follows:

 `c.NotebookApp.certfile = u'/home/username/.jupyter/mycert.pem'
 c.NotebookApp.ip = 'your_server_ip_address'
 c.NotebookApp.open_browser = False
 c.NotebookApp.password = u'gernerated_sha_for_example_sha1:9e59c5ba9186:cecf9600b48b50f076c4481f0ce522d9f091cc90'
 c.NotebookApp.password_required = True`
