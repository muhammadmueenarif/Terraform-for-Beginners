Section 01. Basics and Setup

Lecture 01. 
Why terraform?
In simple terms, Terraform lets you build cloud infrastructure. Like you will write a few lines of code and 
you will run a command on CLI. You will run a command and cloud environment will be ready with different services 
which you need.

It's basically like instead of clicking through different screen. suppose you have to create an EC2 on the 
AWS. You click on different screens. You just go on the EC2 services. Then you enter the name of the EC2.
After that, you create a security group, all these things.
So instead of doing all those things, we will simply write a code and that we can use it anywhere we want.


Benefits
First is speed and consistency.
let's say you want to deploy an EC2 okay.And also database.
So we want to create like RDDs any relational database like Oracle Postgres. And also want to deploy a load 
balancer.

So the challenge here is you have to deploy this infrastructure in three different regions or more than that.

Suppose you work in any project. So we have different environments. like we have dev. Then we have system integration 
testing. Then UAT. After that, Pre-production as well. and then we have a production environment.

So it's a very time consuming process. So what you will be doing, you will write a Terraform code.
And that code, you can use it to deploy in all these three environments, or more than three environments.
And you can use that everywhere.
So it's just like write once and use it at multiple places.


Let's talk about next reason version control.
it is just like the application code. Like we deploy the application code in the git. then we have different 
versions of it. So if something goes wrong then we just roll back and we go into the previous version.
So that also you can do with the help of Terraform, you can integrate with the git.


The reason three we have is cloud support.
We have different cloud providers in a market. if you see around you will hear AWS, GCP, Azure.
So with the help of Terraform you can connect with all these three cloud providers. And you can create your 
infrastructure on any of the platform or any of these cloud provider.

If we talk about real use cases and also companies like Netflix, Uber, all these companies creates their infrastructure 
in the production environment using Terraform.



Lecture 02. What is IaC?
Infrastructure as a Code. 
Let's imagine this. You are setting up a new project in AWS. And you have to set up EC2. So we follow some 
of the steps like we search for that service. Then we open the console and click on launch EC2. Then we 
select the Ami. Right after that we select uh the networking settings we configure like which ports to open, 
then security groups. And then we hit the launch button launch EC2. Then it creates EC2 instance for us.

So just imagine this thing like every single time you want to do this. And that too for all the different environments 
where the configuration will be same everywhere.

Suppose we have five different environments like dev, UAT, Preproduction, prod. it's a very painful thing 
to do the same thing again and again. if you miss any configuration, that is also a big thing.

So what basically a Terraform do or any infrastructure as a code tool do. we can just define a code okay.
We can write a code. in that code we can define like create a VPC. Then what are the networking configuration. 
we can define security thing. And also we can choose any gateway we want to use in our infrastructure.
So all these things we can define into a code. And we'll get our infrastructure ready.
And beauty thing is it's repeatable.
And also you can do the same thing in all the different environments. So you have to write once and use it at multiple places.

So what IAC does. So it turns your Infrastructure into code which means you can treat it just like your app code.
Test it, review it, and automate it.

And tools like like we have different, uh, IC tools like, uh, in this course which will we are going to talk 
about the Terraform. But other tools are also there like CloudFormation. It's from AWS. Then we have GCP also 
like Google Cloud Cloud Deployment, and also we have some Plumie tool.

So we have different types of tools for this thing. we are basically going to focus on this Terraform.
So in short infrastructure code is nothing but automation plus consistency plus speed. And also traceability.



Lecture 03. Terraform Workflow / Working of Terraform
So the thing is like Terraform as a translator between your code and your cloud provider, whether it's
AWS, Azure or GCP. So we'll be writing a code and this code will create our infrastructure for us like servers, 
databases, storage buckets and so on.
So it can be any cloud provider either AWS Azure or GCP.

we start by writing our.tf file. So we create a file with the.tf extension for any terraform file. And in 
this file we describe our requirement. Like we describe we need one EC2 instance one or S3 bucket we need.
So basically we describe the infrastructure in this file.
after that we run a few commands. 
1. terraform init.
These are the basic commands which we will be use for like every time we will use this.

terraform init is used to initialize the project. once we will install the terraform then we'll see it.
it is used to initialize the project.

Next we have 
2.Terraform plan. 
it is used to preview what changes Terraform is about to make. it preview thing like what are the changes 
going to happen if we will run. If you will run this particular command then we have 

3. Terraform apply.
So as the name suggest, It will basically provision or change your infrastructure or create your infrastructure.


Next we have a 
4. Terraform destroy.
why destroy. Suppose you don't want to use your infrastructure after some time, like after your shift is over 
or something like that. So if you don't want to use it and you want to save cost, then in that case you will 
use the Terraform Destroy. It will tear it all down.

Whatever infrastructure you have created, all will get vanished and deleted. 
So what is what's interesting is so interesting part here is Terraform keeps track of what is what's
deployed using something called a 

state file.

So this is one of the important concept state file. in this what happens. it's just like a memory, like you 
can say as the Terraform memory,
it knows what resources it has created so that it doesn't create any duplicate resource and it doesn't 
delete any wrong resources.
And it all happens through a provider plugin. So basically we have a provider plugins like we have AWS 
plugin Azure and GCP all. so it works with the provider plugins.

We'll see providers in our next classes.

So the basically the cycle is first we'll write the terraform code.
Then we have a plan. Then we will be applying. Then we'll get the infra. Then we can track it via state file.
But first we will install Terraform. 