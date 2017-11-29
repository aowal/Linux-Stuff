## Important Linux commands I have to use everyday


#### Create a new user

 ```
 adduser username
 ```
  
#### Add the user in sudoers list
  
 ```
 usermod -aG sudo username
 ```

#### Check we can use sudo by switching to the newly created user
  
 ```
 su - username
 ```
 
 #### Add a new virtualenv to jupyter notebook
  
 ```
 source path-to-venv/bin/activate
 pip install ipykernel
 python -m ipykernel install --user --name=venv-name
 ```
  
