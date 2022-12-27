# we use ssh agent forwarding, we don't copy ssh private key of private instance to bastion host
  - we add key to ssh-agent using command line `ssh-add -k path_to_file_pem` and check file added completed using `ssh-add -L`
  - from local computer we connect to bastion host using command `ssh user@bastion_host`
  - from bastion host we connect to private instance using command `ssh user@private_instance_id`
