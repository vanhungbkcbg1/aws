# we use ssh agent forwarding, we don't copy ssh private key of private instance to bastion host
  - we add key to ssh-agent using command line `ssh-add path_to_file_pem` and check file added completed using `ssh-add -L`
  - from local computer we connect to bastion host using command `ssh -A user@bastion_host`
  - from bastion host we connect to private instance using command `ssh user@private_instance_id`
  - we can connect from `local` -> `server1` -> `server2` -> `server3`.... using **ssh agent forwarding**, in this case we have to do as follow  
  **In local** we will use command like this  
  `ssh -A user@server1`  
  **In server1** we will use  
  `ssh -A user@server2`  
  **In server 2** we will use  
  `ssh user@server3`
  
