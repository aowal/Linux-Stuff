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
 
  #### Download a file from google drive using curl; replace {FILEID} with google drive id}
  
 ```
 curl -JLO 'https://docs.google.com/uc?export=download&id={FILEID}'
 ```
 
   #### Download a file from google drive using wget; replace {FILEID} with google drive id and {FILENAME} with your_filename
  
 ```
 wget --no-check-certificate 'https://docs.google.com/uc?export=download&id={FILEID}' -O FILENAME
 ```
   #### Copy file or folder using ssh from a remote server
  
 ```
 scp -r {USERNAME}@{SERVER_IP_ADDRESS}:{REMOTE_SERVER_PATH_TO_THE_DIRECTORY} {LOCAL_PATH_OF_THE_DIRECTORY}
 ```
   #### Sent file or folder using ssh to a remote server
  
 ```
 scp -r {LOCAL_PATH_OF_THE_DIRECTORY} {USERNAME}@{SERVER_IP_ADDRESS}:{REMOTE_SERVER_PATH_TO_THE_DIRECTORY}
 ```
   #### Check for any command after a fixed time with watch; for example
  
 ```
 watch -n .5 htop
 watch -n .3 showq -u username
 ```

   #### Install a python package without root access; it will install the package in the ~/.local/lib/pythonX.X/site-packages directory
  
 ```
 pip install --user {PACKAGE_NAME}
 ```
 
   #### Install a python package in a custom directory; then need to add the path to PYTHONPATH environment variable
  
 ```
 pip --trusted-host pypi.python.org install --target="{CUSTOM_DIRECTORY_PATH}" opencv-python
 export PYTHONPATH="{CUSTOM_DIRECTORY_PATH}":$PYTHONPATH
 ```
   #### Or you can append the path to the sys.path in your python script
  
 ```
import sys
sys.path.append("{CUSTOM_DIRECTORY_PATH}")
 ```
   #### Running a script with nohup in background with output redirrection(and error too) to a file 
  
 ```
nohup python {SCRIPTNAME} > {OUTPUT_FILENAME} 2>&1 &
 ```
 
   #### If then at anytime you can stop it by killing with the following command:
  
 ```
kill -9 {PID}
 ```
 
   #### Delete files from a directory based on another directory those match a criteria(common files in two directories)
  
 ```
cd {MATCHING_DIRECTORY}; find . -name '*.png' -exec rm -rf {PATH_TO_THE_DELETE_DIRECTORY}/{} \;
 ```
   #### Download files from a ftp server using ftp
  
 ```
ftp {FTP_SERVER_NAME_OR_IP}
  user: {USERNAME}
  password: {PASSWORD}
cd {PATH_TO_FILE}
get {FILE_NAME}
 ``` 
   #### Download files from a ftp server using wget, can use -r to download recursively and -v for verbose output
  
 ```
wget -r ftp://{USERNAME}:{PASSWORD}@{FTP_SERVER_NAME_OR_IP}/{PATH_TO_FILE_OR_FOLDER}
 ```
   #### Download files from a ftp server using curl, can use -r to download recursively and -v for verbose output
  
 ```
curl -v -JLO -u {USERNAME}:{PASSWORD} ftp://{FTP_SERVER_NAME_OR_IP}/{PATH_TO_FILE_OR_FOLDER}
 ```
   #### Find folders with a name
  
 ```
 find . -type d -name "{FOLDER_NAME}"
 ``` 
   #### Comment block in Vim
  
 ```
1. First, go to the first line you want to comment. Then, press Ctrl + V to put the editor in the VISUAL BLOCK mode.
2. Then using the arrow key and select until the last line.
3. Now press Shift + I to put the editor in INSERT mode and then press #. This will add a hash to the first line.
4. Then press Esc, and it will insert a # character on all other selected lines.
 ``` 
   #### Uncomment block in Vim
  
 ```
1. Put your cursor on the first # character, press Ctrl + V , and go down until the last commented line. 
2. Then, press x, that will delete all the # characters vertically.
 ``` 
   #### Find size of folders in a directory and sort them by size
  
 ```
 find . -type d -name "{FOLDER_NAME}" 
 
 sudo du -hsc * | sort -hr
