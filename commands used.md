### MOST USEFUL COMMANDS(if  you know logically what to do):
  
    - aws help
    - aws  [command] help
    - aws  [command]  [subcommand] help

### to create a key

> aws ec2 create-key-pair --key-name < keyname  >



### to create a security group

> aws ec2  create-security-group --description  < description >   --group-name < groupname >



### to add an ingress rule

> aws ec2 authorize-security-group-ingress --group-id  < security group name > --protocol < protocol name > --port < port number >  --cidr   < cidr range >



### to launch an instance with the created security-group and the key



> aws ec2 run-instances  --image-id    < ami id >         --instance-type < instance type >   --count < number of instances to launch with same configurations>  --security-group-ids  < security group id >  --subnet-id < subnet i d>  --key-name < key name >




### to create a volume in the zone where the instance is as it is a zonal service.


> aws ec2 create-volume --availability-zone < the zone should be same as the ec2 instance zone  >  --size < size of the ebs storage > --volume-type <type of the volume : depends on the io speed and other factors >




### to attach to the instance we have launched

> aws ec2 attach-volume   --volume-id <  volume id >   --instance-id    < instance id >    --device < block device name like : /dev/sd[a-z] > 




### first of all we need to detach teh volume we have attached

> aws ec2 detach-volume   --volume-id < volume id >




### terminate the instance


> aws ec2  terminate-instances - -instance-id < instance id >




### delete the volume


> aws ec2  delete-volumes --volume-id <  volume id >




### delete the security group


> aws ec2  delete-security-group --group-id < security group id  >




###  delete the key


> aws ec2 delete-key-pair --key-name <  key name  >
