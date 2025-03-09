Why We Need This AWS VPC Automation Script & What Problems It Solves

Cloud infrastructure is the backbone of modern applications, and setting up a Virtual Private Cloud (VPC) in AWS is a fundamental requirement for deploying secure, scalable services. However, manually creating a VPC and its networking components via the AWS Management Console is time-consuming and error-prone. This script automates the process, ensuring consistency, efficiency, and security while eliminating manual errors.

⸻

1. What Problems This Script Solves

❌ Problem 1: Manual VPC Creation is Tedious and Error-Prone
 • Without automation, cloud engineers must manually configure networking settings via the AWS Console, which is slow and inconsistent.
 • A single misconfiguration can lead to security risks or broken networking.

✅ Solution:
 • This script automates the entire process, ensuring that networking components (VPC, subnets, internet gateway, route tables) are set up correctly and consistently.

⸻

❌ Problem 2: Risk of Creating Duplicate VPCs
 • If a VPC with the same name exists, creating another duplicates resources, causing confusion and unnecessary AWS costs.

✅ Solution:
 • The script checks for an existing VPC before creating a new one.
 • If the VPC exists, it retrieves and reuses it instead of creating a duplicate.

⸻

❌ Problem 3: No Internet Access in Default VPCs
 • AWS does not automatically configure internet access in a custom VPC.
 • Without an Internet Gateway (IGW), instances cannot connect to the internet, making it impossible to install packages or communicate with external services.

✅ Solution:
 • The script creates and attaches an Internet Gateway, allowing internet connectivity for instances in the VPC.

⸻

❌ Problem 4: No Automatic Routing for Internet Traffic
 • Even if an Internet Gateway is attached, AWS does not automatically configure the routing.
 • Without a route table directing internet traffic to the gateway, instances remain isolated.

✅ Solution:
 • The script creates a Route Table and configures a default route (0.0.0.0/0) to allow internet access.

⸻

❌ Problem 5: Manually Assigning Subnets is a Hassle
 • AWS requires subnets to be created in specific availability zones (AZs).
 • Choosing AZs manually for high availability is cumbersome.

✅ Solution:
 • The script automatically creates three subnets across multiple availability zones (ap-northeast-2a, 2b, 2c).
 • This ensures fault tolerance—if one AZ fails, the others remain operational.
