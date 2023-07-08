# Building A Static Website Using Amazon S3 And Route 53
<img width="893" alt="1" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/1da76257-d359-45e8-8d66-bcae2ba93aba">

In this project, I will demonstrate step by step my abilities to build a static website using AWS services such as Amazon S3 and Route 53. The benefits of using these services are that they provide a scalable, secure, and cost-effective solution for hosting and managing static websites.

<b>Amazon S3 (Simple Storage Service)</b> is a highly durable and reliable object storage service offered by AWS. It allows you to store and retrieve large amounts of data, including website content such as HTML, CSS, JavaScript files, and media assets. By hosting your static website on Amazon S3, you can take advantage of its high availability and global reach, ensuring that your website loads quickly for users worldwide. One of the main benefits of using Amazon S3 for hosting static websites is its cost-effectiveness. With its pay-as-you-go pricing model, you only pay for the storage and data transfer you actually use, making it an affordable option for small to large-scale websites. 

<b>Route 53</b> is AWS's scalable domain name system (DNS) web service. It allows you to manage and route traffic to your website by associating domain names with specific resources, such as your Amazon S3 bucket where your website files are stored. By using Route 53, you can easily configure custom domain names for your static website, making it accessible to users through user-friendly URLs like www.yourwebsite.com. In addition to hosting and domain management, Amazon S3 and Route 53 offer various security features. Amazon S3 supports access control policies, allowing you to restrict access to your website files based on user permissions. Route 53 provides DNS-level security features, such as DNSSEC (Domain Name System Security Extensions), which helps protect your website from DNS spoofing and other malicious activities.

## Step 1: Create a custom domain name using Amazon Route 53
First let's log into into the AWS Management console and go into the <b>Route 53</b> service panel. I will first start by registering a domain name, for this demonstration I will register <b><i>niazprojectportolio.click<b></i>.

<img width="1577" alt="2" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/d73a10c8-f320-4367-90b2-f36e511b8d4c">

