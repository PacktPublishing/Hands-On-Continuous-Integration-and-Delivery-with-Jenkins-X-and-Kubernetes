# Hands-On Continuous Integration and Delivery with Jenkins X and Kubernetes [Video]
This is the code repository for [Hands-On Continuous Integration and Delivery with Jenkins X and Kubernetes [Video]]( https://www.packtpub.com/cloud-networking/hands-on-continuous-integration-and-delivery-with-jenkins-x-and-kubernetes-video), published by [Packt](https://www.packtpub.com/?utm_source=github ). It contains all the supporting project files necessary to work through the video course from start to finish.

## About the Video Course
Jenkins X is an exciting and fast way to build applications on Kubernetes. Jenkins X handles the job of configuring Kubernetes to build, test, and deploy your applications, so you can focus on fast delivery and make your applications great!
Kubernetes is powerful but complicated; using it not only to run your application but also to build and test it requires a lot of configuration. Jenkins X provides automation for Kubernetes so you can use it to its full potential without spending all of your time configuring and debugging.
This course adopts a step-by-step approach to show you how to use Jenkins X, with plenty of hands-on examples that you can use for your own applications. You'll start with a simple example application deployed to Kubernetes using Jenkins X, then build up to awesome features such as preview environments, promotion, and monitoring. With this course, you can learn Jenkins X fast, and immediately apply what you've learned. <br/>

<H2>What You Will Learn</H2>
<DIV class>

<UL>
• Install and configure Jenkins X in a cloud environment with Google Cloud Platform
• Build an application with Jenkins X, or import an existing application so you can get started quickly
• Control how Jenkins X builds and deploys your applications so you can create the build and test pipeline that works for you
• Build preview environments so you can test the latest software changes in your application before you promote it to production
• Managing application updates (including manual promotion, rolling updates, and pull requests) so you can accelerate the delivery of your application<br/>
</LI></UL></DIV>

## Instructions and Navigation
### Assumed Knowledge
This course is for developers, IT/DevOps professionals, or system admins keen to take advantage of Jenkins X and Kubernetes to enhance their Continuous Delivery processes. A basic knowledge of developing and building software is assumed.
This course requires use of a text editor (e.g. Atom); Git client (graphical or command line); and access to Google Cloud Engine and GitHub.

### Technical Requirements <br/>
#### Minimum Hardware Requirements
For successful completion of this course, students will require a computer system with at least the following:

OS: Linux (recommended), Windows, or macOS
Processor: Dual-core processor
Memory: 4 GB
Storage: 120 GB

The course examples demonstrate the installation and use on Linux. To run with the minimum hardware requirements, students will also need the ability to create Kubernetes clusters in a cloud environment.

Recommended Hardware Requirements
For an optimal experience with hands-on labs and other practical activities, students require access to sufficient hardware to run a virtual machine:

OS: Linux (recommended), Windows, or macOS
Processor: Quad-core processor
Memory: 8 GB
Storage: 120 GB

This will permit using Jenkins X and Kubernetes via Minikube. Access to a cloud environment is also strongly recommended.

Software Requirements
The following requirements are recommended to view and edit the example files.

Operating system: Windows, Linux, or macOS
Hypervisor: VirtualBox or Hyper-V
Browser: Chrome or Firefox (latest version)
IDE (Visual Studio Code or IntelliJ recommended)
<br/>

## Important Note

We will be using cloud resources, with the possibility that this will cost
money. Google Cloud Platform has a limited-time free tier, and our
setup will stay within the free tier, but once your free period expires
there will be a cost, which is greater as long as you have nodes in your
cluster's node pool.

To reduce costs while keeping your cluster configuration, you can resize the
cluster's node pool to 0, and then size it back up when you're ready to use
it. Remember to also turn off autoscaling so it doesn't scale back up again,
and revisit the cluster page to make sure the nodes were deleted properly.

Of course, you can also delete your cluster entirely and re-create it using
the instructions in Section 1.

## Application Cleanup

Throughout these videos, we will be creating applications in our Jenkins X
cluster. These applications will continue to run unless deleted or the cluster
is deleted from Google Kubernetes Engine.

To delete applications from Jenkins X, use the `jx delete application`
command. This will prompt you for one or more applications to delete. You will
have to manually remove the Git repository in GitHub.

One note of caution: as of when these videos were recorded, deleting the
application does not completely remove it from Jenkins X. There will still be
files in the boot configuration repository and Helm charts in chartmuseum. For
this reason, it is not safe to delete an application and add a new application
with the same name.

## Related Products
* [Adobe After Effects CC: Tips, Tricks, and Techniques [Video]](https://www.packtpub.com/business-other/adobe-after-effects-cc-tips-tricks-and-techniques-video)

* [Mastering Palo Alto Networks [Video]](https://www.packtpub.com/networking-and-servers/mastering-palo-alto-networks-video)

* [Azure Cognitive Services for Developers [Video]](https://www.packtpub.com/application-development/azure-cognitive-services-developers-video)
