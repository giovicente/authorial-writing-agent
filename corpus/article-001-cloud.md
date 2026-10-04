# Cloud? What Cloud?

The term *cloud computing* is becoming increasingly common in the day-to-day work of IT professionals, and it has gained attention in other fields as well.

Lower spending on proprietary hardware, the ability to scale an application to handle higher request volumes, and easier maintenance are just some of the reasons cloud services have been adopted at scale. They also motivate companies of every size to move their codebases and infrastructure to the cloud.

But what exactly is the cloud? What are its practical benefits? Why is half of my LinkedIn feed made up of colleagues sharing their AWS certification badges? And, for that matter, what is AWS? Is it synonymous with the cloud?

I hope to answer these questions and more in this article.

## So, What Is the Cloud?

By definition, cloud computing refers to computing resources—such as data-processing solutions or storage—provided and consumed on demand.

A simple analogy is a cable TV service. Beyond the package you have already subscribed to and pay for, you can purchase additional content, such as a pay-per-view event, whenever you need it. You can consume what you want, how you want, and in the amount you need.

In more formal terms, a company hires one or more computing services from a provider, uses them in whatever way makes sense for its needs, and pays the bill at the end of the month.

These solutions are delivered through hardware and software—surprise, surprise—distributed across data centers around the world. Those data centers belong to the companies that provide the services and are effectively rented out to businesses or individuals using the resources.

For the customer, the specific data center being used is usually irrelevant. Service providers typically process workloads on machines that are geographically closer and therefore likely to offer better performance. Where the application physically runs is generally beside the point for the customer. One major exception is open banking: in Brazil, legal requirements mandate that data be stored on servers located in the country.

> ☁️ The cloud does not exist—it is just someone else's computer. ☁️

## Why Use the Cloud?

Now that the concept is clear, let us look at the main reasons behind the growing use of these services.

One of the biggest drivers is lower upfront and maintenance costs. Purchasing and maintaining hardware involves expenses such as power, cooling, and physical space. On-demand services can be more cost-effective than the fixed costs associated with owning hardware.

Cloud services also make it possible to tailor resources to the traffic received by a hosted system. If demand spikes—for example, during Black Friday for an e-commerce site—additional machines can be allocated to run the application and absorb the load. That is the well-known concept of scalability. When demand drops, fewer resources can be allocated, which lowers the bill as well.

Another benefit is the ability to monitor and maintain an application through services offered by cloud providers, making the application observable. You can track key metrics, such as how many processing requests succeeded or failed, as well as availability—whether the system is up and running.

## What About IaaS, PaaS, and SaaS?

- **IaaS:** Migrate to it.
- **PaaS:** Build on it.
- **SaaS:** Use it.

These acronyms refer to cloud service models that can be purchased. Each has its own characteristics and trade-offs.

### IaaS: Infrastructure as a Service

IaaS refers to the provisioning of infrastructure, which basically consists of the machines on which customers host their applications. Control over the operating system, environment configuration, versioning, and the application itself remains with the customer. One example is Amazon Web Services' Elastic Compute Cloud (EC2).

### PaaS: Platform as a Service

PaaS provides an environment for deploying applications developed or acquired by the customer, as well as configuring their runtime environment. Unlike IaaS, the provider manages not only the machines but also the operating system, networking, and storage. This removes those responsibilities from the customer. Examples include Heroku—one of the earliest cloud service platforms—and Red Hat OpenShift, which allows applications to be packaged and run in containers (perhaps a topic for a future article).

### SaaS: Software as a Service

In addition to the infrastructure and platform described above, SaaS provides the application itself, whether through a browser, mobile or desktop apps, or APIs. In this case, you simply use it: the application is ready, and the service is already delivered.

A well-known example is Spotify. It can be accessed through its app or a browser, or through integrations with its APIs. If you are developing a system that needs to integrate with Spotify's platform, you can consult its [official documentation](https://developer.spotify.com/documentation/web-api/) and build integrations with the application.

## Where Do AWS, Azure, and Google Cloud Fit In?

AWS, or Amazon Web Services, is a cloud computing services platform. To answer the question from the beginning of this article: it is not synonymous with the cloud. It is one of many service providers. Other examples include Microsoft Azure, Google Cloud Platform, and tools already mentioned here, such as Heroku. An application can use and integrate services provided by more than one platform.

As we have seen throughout this article, cloud computing is the use of computing resources on demand. Platforms such as AWS are the suppliers of those resources. They provide environments and a wide variety of cloud solutions, from application hosting to logging and observability tools, databases, file-storage tools, and even more advanced capabilities such as facial recognition and machine learning.

These providers offer training and certifications at different levels. They are excellent ways to strengthen and demonstrate your knowledge of the platforms, and certified professionals are highly valued in the IT market.

Regardless of which platform you choose, however, it is important to understand the core cloud concepts and the available services. Those fundamentals do not change from provider to provider, and they help you make sound decisions about which of the many tools on offer are worth using.

There is still more to cover, including the differences between public, private, and hybrid clouds, as well as the criteria for choosing IaaS, PaaS, or SaaS. To keep this article from becoming too long, I will cover those subjects another time. If this article gets a positive response, I may turn it into a series.

I hope these concepts are now clear. Questions and suggestions are very welcome in the comments.
