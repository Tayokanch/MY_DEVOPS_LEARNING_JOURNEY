# Default VPC & Custom VPC

## Default VPC
- Every `AWS Account` comes with a defauly VPC
- Default VPCs have configuration defined by`AWS`
- This VPC is designed for use by AWS so we can quickly and easily deploy resources
- By default there will be one` Default VPC` per region with /16 IPv4 `CIDR block **172.31.0.0/16**`
- Within **Default VPC**, there will be a **Default Subnet** inside each **Availabity Zone** in that region with /20 IPv4 Range
- **Internet Gateway** is always attached to the `Default VPC`
- We are also going to have a `route (0.0.0.0/0)` that points all traffic to thhis `Internet Gateway`
- Therefore, any resources in these **default subnets** will be accessible from the internet by default


## Custom VPC
- This VPCs allow us to create / modify all configurastion associated with the VPC