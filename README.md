# Bluegreen-deployment


How Does a Blue/Green Deployment Process Work
The main prerequisite for a blue/green deployment has two identical production environments, with a router, load balancer, Ingress that can switch traffic between them. 

The blue/green deployment process works as follows:

Deploy new version—deploy the new (green) version alongside the current (blue) version. Test it to ensure it works as expected, and deploy changes to it if needed.
Switch over traffic—when the new version is ready, switch overall traffic from blue to green. This should be done seamlessly so end-users aren’t interrupted.
Monitor—closely monitor how users interact with the new version and watch out for errors and issues.
Deploy or rollback—if there is a problem, immediately roll back by switching traffic back to the blue version. Otherwise, keep traffic on the green version and continue using it. The green version now becomes the blue (current) version, and a new version can be deployed alongside it as the “new green” version.



# Diagrams explanation

There are two  types of the diagram in this repo; I am going to explain what is the whole idea of them.
1- there is a complete diagram with all teh component of your eks infrastructure in AWS as a cloud service solution; most of those services I chose since there is a lot of advantages of using them since the third part tool provide more reliability to the company in terms you don't need to depend of only one single service 

-Gitlab CICD delivering 
-Slack  notification channel 
-Terraform for Iac 
-Argos CD for Rollouts 

# Using blue/green deployments for progressive delivery

