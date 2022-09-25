<center><b>Access S3 bucket from private VPC endpoint</b></center>

1. Create a S3 bucket that need to be access by instance
![](https://i.imgur.com/h3BtoOt.png)

2. Create a IAM role that need to access S3 services
![](https://i.imgur.com/BW5nRx2.png)

3. Create a Endpoint for S3 bucket access
![](https://i.imgur.com/ydiif92.png)

4. Add the Endpoint in VPC route table
![](https://i.imgur.com/p3kLThm.png)

5. Create 2 instance (both from Amazon linux image) make one for public and another for private
![](https://i.imgur.com/PogYcFK.png)

6. Make the private instance with an IAM role attached that we create to access the S3 bucket. Now finally check if you able to access the S3 buckets from the instance private instance
![](https://i.imgur.com/p47mbs1.png)

    It is able to access the S3 bucket from the private location.

