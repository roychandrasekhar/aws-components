<center><b>Peering connection between two private VPC in AWS</b></center>

![](https://i.imgur.com/rvt4v74.png)

1. Create 2 VPC in North Virginia region</br>
![](https://i.imgur.com/O1czRtl.png)

2. Create 1 VPC in Oregon region </br>
![](https://i.imgur.com/LRhyOxc.png)

3. Peering connection between MYVPC1 and MYVPC2
![](https://i.imgur.com/TWLFPDk.png)

4. Test if the peering connection work by creating instance between them
![](https://i.imgur.com/ObOO5AW.png)

    connection only work after
    From Adding Peering connection in MYVPC2 routable of if we want connection from MYVPC2

5. Now test connection between MYVPC2 to VPCOregion1 between instances 
   1. First connect into VPCOregon1
      ```ssh -i chandra\_secret\_oregon.pem ubuntu@35.86.90.42```
   2. Then from there try to connect into MYVPC2 *( \* of course you should pass the secret file by SCP)*
      ```ssh -i chandra\_secret.pem ubuntu@130.0.125.131```
      
    ![](https://i.imgur.com/l32Voun.png)


