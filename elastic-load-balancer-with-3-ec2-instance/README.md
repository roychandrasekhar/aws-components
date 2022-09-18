Elastic Load Balancer with 3 EC2 instance
 
1. Create 3 RC2 instance</br>
![](https://i.imgur.com/mZiOs7Q.png)

2. Create Classic Load Balancer and map this with all of this instance
![](https://i.imgur.com/5cT68bp.png)
![](https://i.imgur.com/MS0BAPM.png)

3. Now copy the DNS url and run in browser, e.g
   Chandra-classic-load-balancer-1737339893.us-east-1.elb.amazonaws.com/index.php
   1. ![](https://i.imgur.com/jERorm1.png)
   1. ![](https://i.imgur.com/5CPmyJ5.png)
   1. ![](https://i.imgur.com/oo5QMyl.png)

On every refresh of the Classic load balancer DNS url will load all instance in round robin fashion

4. Now migrate the classic load balancer into Application load balancer. Click on the Migration tab in the classic load balancer and click “Launch ALB Migration Wizard”</br>
   ![](https://i.imgur.com/TV8V1W8.png)
5. ![](https://i.imgur.com/YHF8Bkg.png)
6. Copy the new Application load balancer DNS url and check in the browser</br>
7. ![](https://i.imgur.com/x0JcwXG.png)


