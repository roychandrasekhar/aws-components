<center><b>Create bastion host in AWS VPC</b></center>

![](https://i.imgur.com/1kjmSgn.png)

![](Aspose.Words.a81c27dd-ecb1-476a-956e-792f8dc40fb8.001.png)

1. Create VPC
![](https://i.imgur.com/mX9Z6oy.png)

2. Create Internet gateway!
![](https://i.imgur.com/4LR5Scz.png)

3. Then attach the Internet gateway to our VPC
![](https://i.imgur.com/SMsqLrg.png)

4. Now create two Subnets as mention
![](https://i.imgur.com/uo7c6Rn.png)

5. Then create 2 route tables one for public and one for private subnet.
First create a public route table
![](https://i.imgur.com/Jo3JQe1.png)

    Associate the route table with public subnet from “Subnet associations”

    Edit the route table and add destination “0.0.0.0/0” and assign our Internet gateway to this
![](https://i.imgur.com/nagBVuy.png)

    Now create the private route table and associate it with our private subnet
![](https://i.imgur.com/uzCFOo6.png)

    \* Here we don’t need to add our internet gateway to the private route table because this subnet need to be stay in private mode.

6. Now create two instance to make it confirm its private and public from internet access
![](https://i.imgur.com/n4Ncj1A.png)

7. Copy the secret file into public instance by scp
    ```scp -i chandra\_secret.pem chandra\_secret.pem ubuntu@54.83.105.56:/home/ubuntu/```

8. SSH into private instance from public instance on private instance private IP and try to ping www.google.com
    ```ping www.google.com```
    
    ![](https://i.imgur.com/uhO01mS.png)

    So it failed. Means its private and cant access any internet.

9. Now create a NAT gateway in public subnet, because NAT gateway itself need the internet and then only it can allow internet access
    ![](https://i.imgur.com/n7Lv8Pl.png)

    And add this NAT gateway to the private route table so that private instance can access the internet through this NAT gateway
    ![](https://i.imgur.com/Ff9n1xW.png)

10. Now SSH back into private instance and try again to ping google.com
![](https://i.imgur.com/SHeIby3.png)

11. To achieve this I have to add one inbound rule to make it work, IPv4 ICMP. After this only i can access internet in this private instance
![](https://i.imgur.com/Xrl8aDg.png)

