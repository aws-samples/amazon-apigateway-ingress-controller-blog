## API Gateway as ingress controller for EKS 

Amazon Elastic Kubernetes Service (Amazon EKS) makes it easy to deploy, manage, and scale containerized applications using Kubernetes on AWS (https://aws.amazon.com/kubernetes/). When teams deploy micro-services on EKS, they usually expose REST APIs for use in front ends, and third-party applications. A best practice is to manage these APIs with an API gateway (https://aws.amazon.com/api-gateway/). 

This provides a unique entry point for your APIs and also eliminates the need to implement API-specific code for things like security, caching, throttling, and monitoring for each of your micro-services.  You can implement this pattern using ALB Ingress Controller (https://aws.amazon.com/blogs/opensource/kubernetes-ingress-aws-alb-ingress-controller/) and Amazon API Gateway. Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. This approach works but it requires you to manually create several configuration files. How can we automate this task?

In this post, we’ll show how to use an open-source solution APIGateway Ingress Controller (https://github.com/awslabs/amazon-apigateway-ingress-controller), which reduces the manual steps by quickly configuring  your APIs running on Amazon EKS by leveraging the HTTP proxy mode of Amazon API Gateway. APIGateway Ingress Controller (https://github.com/awslabs/amazon-apigateway-ingress-controller) configures a Network Load balancer in front of a reverse proxy pod which handles the path-based routing and routes HTTP requests to the pods. The following diagram shows the high-level architecture described in this article:


## License Summary

The documentation is made available under the Creative Commons Attribution-ShareAlike 4.0 International License. See the LICENSE file.

The sample code within this documentation is made available under the MIT-0 license. See the LICENSE-SAMPLECODE file.
