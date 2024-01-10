# Systems Hardening with Patch Manager via AWS Systems Manager

## Lab overview
In organizations with hundreds and often thousands of workstations, it can be logistically challenging to keep all the operating system (OS) and application software up to date. In most cases, OS updates on workstations can be automatically applied via the network. However, administrators must have a clear security policy and baseline plan to ensure that all workstations are running a certain minimum version of software. We use Patch Manager, a capability of AWS Systems Manager, to create a patch baseline. You then use the patch baseline that you created to scan the Amazon Elastic Compute Cloud (Amazon EC2) instances for Linux and Windows that were pre-created for this lab.The primary focus of Patch Manager is to install OS security-related updates on managed nodes. 


## Task 1: Created six EC2 instances: three instances with the Linux OS and three with the Windows OS
![ec2 instance created](https://github.com/Cloud-Xplorer08/Security-Systems-Hardening-/assets/71820244/f04efb8a-cec2-4b70-88eb-d7166e2ed6f9)

## Task 2: Tag instances
We tag our Windows instances. Later, we create a patch group and associate it with these tags. 
![windows tags added](https://github.com/Cloud-Xplorer08/Security-Systems-Hardening-/assets/71820244/b30015fe-1c33-4ff9-a32b-6754b076d121)

## Task 3: Create a custom patch baseline
![baseline created](https://github.com/Cloud-Xplorer08/Security-Systems-Hardening-/assets/71820244/117ef5ef-14a0-4970-9fed-ce5bf321082c)

![add another rule](https://github.com/Cloud-Xplorer08/Security-Systems-Hardening-/assets/71820244/24a1bd8f-7e34-4974-b8c6-dfe067b508bb)

## Task 4: Configure patching
We patch the Linux instances using the Patch now feature and by specifying the key/value pair that the Linux instances are all tagged with. You then patch the Windows instances, also based on the tag associated with them.
After configuration, Patch Manager uses the Run Command to call the RunPatchBaseline document to evaluate which patches should be installed on target instances according to each instance's operating system type directly or during the defined schedule (maintenance window).


