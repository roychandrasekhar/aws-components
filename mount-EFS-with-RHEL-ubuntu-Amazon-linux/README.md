# Mount EFS drive with Amazon Linux, RHEL and Ubuntu

1. Launch 3 instance in Ubuntu, Red Hat, Amazon Linux
![](https://i.imgur.com/DqEmpyj.png)

2. Create a new security group for port 2049 open for both inbound and outbound rule
   ![](https://i.imgur.com/YQqi3eh.png)

3. Create EFS volume by using the same security group for all the required availability zone under which this EFS volume need to mount
![](https://i.imgur.com/DKfDdBZ.png)

4. ![](https://i.imgur.com/C8U8yEh.png)

5. Install required application mounting to connect the EFS volume in instance
   1. Ubuntu
      1. apt-get install nfs-common -y
      1. mkdir efs20gb
      1. mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport fs-01c96d247df506782.efs.us-east-1.amazonaws.com:/ efs20gb/
![](https://i.imgur.com/nRNDWn6.png)

6. Amazon Linux
   1. yum install -y amazon-efs-utils
   1. mkdir efs20gb
   1. mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport fs-01c96d247df506782.efs.us-east-1.amazonaws.com:/ efs20gb/
![](https://i.imgur.com/JshFYHP.png)

7. REHL
   1. yum -y update
   1. yum -y install nfs-utils
   1. mount -t nfs4 -o nfsvers=4.1,rsize=1048576,wsize=1048576,hard,timeo=600,retrans=2,noresvport fs-01c96d247df506782.efs.us-east-1.amazonaws.com:/ efs20gb/

![](https://i.imgur.com/T76mu4q.png) 

