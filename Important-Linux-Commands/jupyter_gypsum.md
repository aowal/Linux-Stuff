# How to access jupyter notebook in gypsum using SSH tunneling

## First get a local node using srun(or, you can submit it as a batch job too)

### In local node, run this command

 ```
 jupyter notebook --no-browser --port=8889 --ip=0.0.0.0
 ```

 Here, you will see that the jupyter will open in http://{gypsum_node_id}:8889

Remember this {gypsum_node_id}, as you will ssh to this node from your local computer

### In your local computer, open terminal, then type
  
 ```
 ssh -N -L 8889:gypsum_node_id:8889 username@gypsum.cs.umass.edu
 ``` 
  
### Now open google chrome and type
  
 ```
 localhost:8889
 ``` 

# Optional

## you can create bash alias for the above tasks

### In gypsum ~/.bashrc

```
function jpt(){                                                           
    # Fires-up a Jupyter notebook by supplying a specific port      
    jupyter notebook --no-browser --port=$1 --ip=0.0.0.0
}
```

### So, you can run

```
jpt port_id
```

### In you local computer's ~/.bashrc, you can put this alias

```
function jpt_server (){
    ssh -N -L $1:$2:$1 aowal@gypsum.cs.umass.edu
}
```

### So, you can run

```
jpt_server port_id gypsum_node_id
```
