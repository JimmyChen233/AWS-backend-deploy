![image](https://user-images.githubusercontent.com/57895489/148780221-e953d0e3-1079-4305-87b4-292e71b5c093.png)

# Set up networks 

**Create a VPC**
![image](https://user-images.githubusercontent.com/57895489/148778127-9678341c-4e00-4cdb-b28a-d077f9b05bdd.png)
**Create Subnets**

Subdivide this vpc to 4 subnets, and designate two of those as public subnets where our load balancer will be run and two of those as private subnets where our tasks will be run.

![ap-southeast-2 console aws amazon com_vpc_home_region=ap-southeast-2 (1)](https://user-images.githubusercontent.com/57895489/148779658-f4909faa-45fc-4b89-89d8-2d4c8ce2c152.png)

![image](https://user-images.githubusercontent.com/57895489/148780096-e4dee2ac-6a98-4248-a1c9-f42b69c6ea10.png)

![image](https://user-images.githubusercontent.com/57895489/148780662-4efe9989-2d70-4823-8a92-5c601619b2d6.png)


![image](https://user-images.githubusercontent.com/57895489/148780343-328605a5-1513-434b-9a14-bb9362453652.png)

The subnets should look like this:

![image](https://user-images.githubusercontent.com/57895489/148781044-a5b9a400-3ccb-460b-bab3-90a71a0797f2.png)

**Create an internet gateway**

To make public subnets actually public, we need to attach an internet gateway.

First we create an internet gateway

![image](https://user-images.githubusercontent.com/57895489/148781524-8c25d30d-d18d-4184-9429-9e2ca8a71a27.png)

Then we attach it to vpc

![image](https://user-images.githubusercontent.com/57895489/148781944-9c8a1151-dcd8-4242-97d5-0f905c65a39a.png)

![image](https://user-images.githubusercontent.com/57895489/148782180-b9d75931-3ca3-4c85-a4d9-a9452eb0d3a5.png)

![image](https://user-images.githubusercontent.com/57895489/148782282-8196f489-4aaa-4b05-a5a5-2a1fc54daabc.png)

Then we create a route table and attach it to public subnets.

![image](https://user-images.githubusercontent.com/57895489/148782822-07d61999-6bfe-4ef6-87f1-bda3ed92316f.png)

![image](https://user-images.githubusercontent.com/57895489/148782893-351b8603-0b59-42a1-8129-ffbeff717c30.png)

![image](https://user-images.githubusercontent.com/57895489/148781944-9c8a1151-dcd8-4242-97d5-0f905c65a39a.png)
