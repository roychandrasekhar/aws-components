Create AWS EC2 instance and mount additional EBS volume

1. Launch Ubuntu instance
![](https://i.imgur.com/gTiX7rA.png)

2. Create 20 GB volume

![](https://i.imgur.com/KVgZL0R.png)

3. Attach volume from the menu

![](https://i.imgur.com/LwKKBzF.png)

4. SSH into instance and check the volume by “lsblk” and “df -h”

![](https://i.imgur.com/yjEE939.png)

5. The volume is attach an visible but not usable until its not mounted properly in the linux system, run following commands
   1. file -s /dev/xvdf
   1. mkfs -t ext4 /dev/xvdf
   1. mkdir ebs2volume
   1. mount /dev/xvdf ebs2volume/


![](https://i.imgur.com/iZQ1CPo.png)![](https://i.imgur.com/pPxfRhh.png)


