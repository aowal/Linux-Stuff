# Run jupyter notebook in remote server with SSH tunneling


### In remote host, open the terminal and type:

`jupyter notebook --no-browser --port=8889`
  
### In your local computer, open terminal, then type:
  
  `ssh -N -f -L localhost:8888:localhost:8889 username@your_remote_host_ip`
  
### Now open google chrome and type:
  
  `localhost:8888`