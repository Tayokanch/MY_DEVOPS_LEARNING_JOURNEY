# Firewall in AWS

- Firewall rules are broken down into `inbound` and `outbound`
- `ibound rules` determines what traffic are allowed into **our devices** and `outbound rules1` determines what traffic are allowed out of **our devices** 
  
## Stateless Firewalls

- lets say we have an application that listens on a *port 443*. when a user wants to send a request to the application, they are going to set the **destination port** to be *port 443*, and set the source port to be some random port among the **ephemeral ports**.
  
- When the server gets a request, it's going to send back a response by setting the `source port (application Port)` to 443 and destination port to be one of the  **ephemeral ports**.
  
- So for **Stateless Firewalls** they must be configured to allow both `inbound traffic`  and `outbound traffic`


## Statefull Firewalls

- Tracks connections
  
- when request comes in on the Inbound direction on port 443, We dont need to set the outbound rule .i.e 
  
- if a request is permitted to come in to our server, the response is automatically permitted to go out in a statefull firewall, therefore no need for **outbound rules**


## Firewall Services on AWS

1. `Network Access Control List (NACL)`: These are firewalls that operate on the subnet level. i.e they filter traffic entering and leaving a subnet
    - They do not filter traffic within a subnet i.e if we have `2 servers` with a **subnets** they will automatically be able to talk to one another.

    - They are `Stateless Firewall`, therefore, rules must be set for both *inbound* and *outbound* traffic
  
2. `Security Group`:
   - Security Group act as a firewalls for individual resources(`EC2`, `LB`, `RDS` etc). Its an individual Firewall for each resources on our AWS Infrascture i.e each Resources on our AWS get their own Firewall rules to Protect the Resources and filter out what is allowed to to communicate within and External 

    - Security Group are Statefull Firewall
    - We can apply multiple security group to a resource and we could also apply one security group to multiple resources

# NACL and Security Group

- When we use `Security Group` as a firewall for individual Resource in our subnets, we Could use `NACL` for subnet - subnet communcation and for filtering traffic entering and leaving each subnet