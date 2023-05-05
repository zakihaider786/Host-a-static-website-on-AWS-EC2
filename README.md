
# Host a static website on AWS EC2



## Screenshots

![App Screenshot](https://user-images.githubusercontent.com/128976395/236316942-62280f43-58c0-4458-b4a6-8da54212e374.png)

As you may have already noticed, cloud computing is strong and extensive, and it will continue to develop and offer numerous advantages in the future. Cloud computing is incredibly economical, and businesses can use it to expand. Cloud computing has a promising future and will benefit both the host and the client.
I made the decision to share some helpful information that might aid you in getting going.
Many of you have probably developed straightforward websites that you can only access locally on your PC or laptop.

But what if you put it in the cloud, where anyone may view it?

🤔 Wait in the cloud.

"You did hear it right, yes"




## About Machine/Service

A web service called Amazon Elastic computation Cloud (Amazon EC2) offers scalable computation capability in the cloud. For developers, it is intended to make web-scale cloud computing simpler. Simply simply, think of it as a different computer that has remote access that is located somewhere.

### But why Amazon EC2?

As you are aware, setting up and maintaining a server is expensive. And it's more crucial for a company or an individual to concentrate on business strategy than it is to concentrate on the infrastructure. AWS is useful in this situation. By enabling you to only pay for capacity that you really use, Amazon EC2 transforms the economics of computing. With the help of Amazon EC2, developers can create apps that are resistant to common failure scenarios.
So let's get to the topic and stop with the briefings.

#### And here we go 👉

##### 10 Steps to Deploy



## Step-1: Choose AMI (Amazon Machine Image)

As a result, we will configure our virtual server as we will be launching our website on a virtual machine. Since Amazon is providing the hardware for the virtual server, our task at this point is to choose the operating system for our server. AMI is an operating system image that is similar to the ISOs for Windows and Linux that we can download and install on our PCs, to put it simply.
(AWS Educate or the free tier of an account is a prerequisite.)

Now set it up by following these steps:

1) In the AWS Management Console on the Services menu, click EC2

2) At the top right of the screen, if you see New EC2 Experience toggle to use the new UI, if it is not enabled by default.

3) Click Launch instance > Launch instance.

4) Click Select next to Amazon Linux 2 AMI 


## Screenshots

![ss2](https://user-images.githubusercontent.com/128976395/236384441-1ef845bf-3a5b-4ba5-ae73-369e51078488.png)


## Step-2: Choose an Instance Type

Amazon EC2 gives a wide determination of occasion types enhanced to fit different use cases. You have the flexibility to select the appropriate combination of resources for your applications by using instance types, which include a variety of combinations of CPU, memory, storage, and networking capacity.
Choose t2.micro.

![1626150750738](https://user-images.githubusercontent.com/128976395/236384600-5789d14d-70f1-49bd-b670-7bb6c3de00bc.png)


## Step 3: Configure Instance Details

This page is used to configure the instance to suit your requirements. This includes networking and monitoring settings. For now we will go with the default setting so click on Next: Add Storage.



## Step 4: Add Storage

Amazon EC2 stores data on a network-attached virtual disk called Elastic Block Store.
You will launch the Amazon EC2 instance using a default 8 GiB disk volume. This will be your root volume (also known as a 'boot' volume).
No alt text provided for this image
Now click on 

![1626151097265](https://user-images.githubusercontent.com/128976395/236384635-afa1eaf9-e83d-4360-9a40-9c29368d62fd.png)


Next: Add Tags

## Step 5: Add Tags

Now click on add tag and set the name according to your wish.


Click on Next: Configure Security Group
## Step 6: Configure Security Group and Launch the instance (Important part)

Click on Add Rule and from the dropdown select HTTP and HTTPs.

![1626151587422](https://user-images.githubusercontent.com/128976395/236384668-402bfb2d-ccd1-4276-bed0-8b602b6ea716.png)


Now Click Review and Launch > Launch

You will be greeted with the following screen 👇🏻

![1626151999180](https://user-images.githubusercontent.com/128976395/236384677-e06d8380-f1c5-4df7-8265-ea349d8cef04.png)

Click on "Create a new pair" and give a name say "linuxkey" to it.
Now click "Download Key Pair" and note the folder where it gets downloaded as we will need it later.
Scroll down and select "Launch"
Navigate to instances and wait for a few minutes for the instance to spin-up.

![1626152422975](https://user-images.githubusercontent.com/128976395/236384688-95d3bac0-21b3-488b-923c-d67c2c99667b.png)

You will see something like this if everything is configured correctly 👆🏻


## Step 7: Connecting to the Instance

Now that your instance is up and running the time has come to connect.
We have several different ways to connect to an instance using putty, powershell, and even directly through the Amazon Console. But here I have used the powershell method as it's convenient for me

### Amazon Linux Code

## Chanage your self to root user

#### sudo su -

![1](https://user-images.githubusercontent.com/128976395/236393567-ffd8bbf5-d2aa-4c5e-943b-feaa5ac65fcc.png)

## Resolve some Dependencies
-----------------------------------------------------

#### yum update -y

![2](https://user-images.githubusercontent.com/128976395/236393572-cf1a3066-af1a-49da-81e4-3c8f68eac661.png)
-----------------------------------------------------

#### yum install -y httpd

This code help to install some packages like (Architecture , Reposetries , version and their size)

Then check the status of httpd server

------------------------------------------------------------

## Check the status of Server

#### systemctl status httpd

![Screenshot 2023-05-05 122644](https://user-images.githubusercontent.com/128976395/236394649-96667714-f35d-4e09-849a-652027ed1f24.png)

This command help to check tha status of server is active or dead.

____________________________________________________________


## Then Go to Directory

#### cd var/www/html

This command help to check the directory where we saved static websites html code.

![Screenshot 2023-05-05 123705](https://user-images.githubusercontent.com/128976395/236396369-824ca360-2458-4a96-8f61-5993e007e5ae.png)

--------------------------------------------------------

## Then start the httpd Apache Server / Check status service is active aur inactive 

#### service httpd start
#### serive httpd status

![Screenshot 2023-05-05 124058](https://user-images.githubusercontent.com/128976395/236396945-7c41a9e8-ba47-448d-a48e-04fd1a74b33c.png)

__________________________________________________________________

## Then go to instance summery on AWS Interface

Copy the public IP Address and paste on your specific browser.

And check it website is live aur not.

![Screenshot 2023-05-05 124230](https://user-images.githubusercontent.com/128976395/236397812-f8ac5ecd-b4c3-4059-b6c9-3e18102458d6.png)

------------------------------------------



If you can see your website loading, congratulations! You now have a website that is set up in the cloud.
Note: This IP address can be shared with friends, and they can access it.

# "Well done for making it to the end!"
# "Now that the infrastructure is ready, it's up to you to expand it."
# I hope this guide has been of some use to you all. Much affection,

