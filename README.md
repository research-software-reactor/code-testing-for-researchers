# CI - barriers faced by researchers

A research software project developed and maintained by an individual scientist or small research group may struggle to implement effective automated testing due to unsuitability of existing hosted solutions and a lack of available systems administration knowledge to set up a custom solution.

Specific examples of this would be:

* Testing frameworks requiring containerisation where none of the developers have any experience of containers
* Software testing of real-world examples that require more resources than hosted solutions such as Azure pipelines or Travis provide
* Documentation for deploying custom testing on cloud platforms (such as Jenkins on Azure) which is written assuming some sysadmin background and seems opaque to a scientific programmer
* Solutions using kubernetes where developers do not have the time (or inclination) to invest in learning about kubernetes

Further barriers are encountered when there is a basic level of systems administration skill but custom testing platforms have barriers to effective research software testing. For example:

* Large projects lean heavily on github which disables their access due to overuse
* Effective testing needs a variety of vm types, and AKS only supports a single nodepool per cluster
* Handling short-lifetime containers in both cost- and speed-efficient ways within the testing framework is difficult
* Documentation tends to be written assuming application deployment, not research software development

Some projects will fit neatly into existing hosted solutions such as Azure pipelines or Travis. This sprint proposal aims to improve support for the research software projects that need a custom solution to fit their needs, and proposes Jenkins on Azure as a solid basic platform, as strong existing learning materials should be able to be modified to make them more suited to use by research programmers.

## Sprint objectives

* Review the existing Jenkins on Azure documentation, identifying where assumptions are made about basic sysadmin knowledge and making materials more accessable to research programmers
* Produce a learning pathway for a research group wanting automated testing of their software on a real-world, resource-intensive problem
* Identify shortfalls in AKS+Jenkins and Azure pipelines to make them more useful for research software testing


## Learning prerequisites

* [Jenkins on Azure](https://docs.microsoft.com/en-us/azure/jenkins/)
* [Docker on Azure](https://azure.microsoft.com/en-us/services/kubernetes-service/docker/)
* [Jenkins with Docker](https://jenkins.io/doc/book/pipeline/docker/)
* [Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/index?view=azure-devops)
