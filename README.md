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
the second diagram explains what is the idea of using Argos cd 

Blue/green deployments provide zero downtime during deployments and the ability to test your application in production without impacting the stable version. In a typical blue/green deployment on EKS using Kubernetes native resources, a new deployment will be spun up. This includes the new feature version in parallel with the stable deployment (see Figure 1). The new deployment will be tested by a QA team.
Once all the tests have been successfully conducted, the traffic must be directed from the live version to the new version

Please be aware, there are several manual interactions and decisions involved during a blue/green deployment.


Prometheus is a monitoring software that can be used to collect metrics from your application. (Prometheus Query Language)


#Blue-Green Deployment file

I've attached an example how is the process in Argos to call the stable env.
