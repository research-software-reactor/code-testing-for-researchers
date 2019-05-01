# Opening up cloud testing for researchers

Research software needs to be tested effectively. During development, good testing practise helps to quickly identify software problems and maintain code quality. When software is operational, ongoing testing ensures that any evolutionary changes to the software do not break required scientific functionality. Building and testing in a precisely specified environment ensures reliability and reproduceability, critical for generating publishable results.

Cloud resources are often key to good testing, either in the form of hosted testing solutions such as [Azure pipelines](https://azure.microsoft.com/en-us/services/devops/pipelines/) or through access to on-demand resources for infrequent resource-intensive tests where full-time dedicated hardware would be prohibitively expensive.

Standard application development is well supported by hosted testing platforms, and large technical software projects with [Dev Ops](https://en.wikipedia.org/wiki/DevOps) support are well provided for by custom [Continuous Integration (CI)](https://docs.microsoft.com/en-us/azure/devops/learn/what-is-continuous-integration) solutions. Research software often falls into a support hole, being far more demanding on test resources than standard applications, but developed by an individual scientist or small research team with minimal or no background in systems administration and little time or inclination to learn the skills necessary for building and maintaining a non-standard [CI]((https://docs.microsoft.com/en-us/azure/devops/learn/what-is-continuous-integration) implementation. 

Specific examples of this would be:

* Research software that is tested by running cut-down versions of real world problems, but still require an order of magnitude more resources than available on a standard hosted [CI]((https://docs.microsoft.com/en-us/azure/devops/learn/what-is-continuous-integration) worker node
* Test platforms that require software to be [containerised](https://www.docker.com/resources/what-container), but none of the researchers are aware of what containers are or how to implement them beyond basic methods
* Learning materials for deploying custom testing platforms tend to be written for a technical reader and are sufficiently opaque to scientific but non-technical researchers that they do not make use of them
* Test platforms hosted on [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) where researchers are unaware of kubernetes and are put off by the added layer of learning needed to maintain the service

Requiring an individual or small research group to set up and maintain a custom testing platform is generally an inefficient use of their time, and improving hosted testing provision to cater for research software needs is a more efficient route to take. In the case where researchers have a reasonable level of sysadmin knowledge to the point they can reasonably deploy and maintain a custom testing platform (ie, [Jenkins](https://wiki.jenkins.io/display/JENKINS/Meet+Jenkins) on [AKS](https://azure.microsoft.com/en-us/services/kubernetes-service/)) they hit problems arising from the differences between standard applications and research software. For example:

* Large projects lean heavily on [github](https://en.wikipedia.org/wiki/GitHub), which temporarily disables their access due to overuse
* Effective testing needs a variety of [Virtual Machine (VM)](https://azure.microsoft.com/en-us/overview/what-is-a-virtual-machine/) types, and AKS only supports a single [nodepool](https://docs.microsoft.com/en-us/azure/aks/concepts-clusters-workloads#nodes-and-node-pools) per cluster
* Research software containers can be very large and hence difficult to handle in cost- and time-efficient ways
* Documentation tends to be written assuming application deployment, not research software development

## Sprint objectives

* Identify and submit bug reports / feature requests on [Pipelines](https://azure.microsoft.com/en-us/services/devops/pipelines/) where it falls short of research software requirements,
primarily in terms of flexibility on worker node specifications
* Identify and submit bug reports / feature requests for shortfalls in [AKS]((https://azure.microsoft.com/en-us/services/kubernetes-service/) which would improve [AKS](https://azure.microsoft.com/en-us/services/kubernetes-service/)+[Jenkins](https://wiki.jenkins.io/display/JENKINS/Meet+Jenkins) for research software, in particular looking at heterogeneous worker nodes via multiple nodepools
* Generate learning materials for handling large, low-value [container images](https://www.docker.com/resources/what-container) within [CI](https://docs.microsoft.com/en-us/azure/devops/learn/what-is-continuous-integration)
* Generate learning materials which reduce existing technical learning to a level that is accessable and useful to non-technical researchers
* Use [devito](http://www.opesci.org/devito/index.html), [firedrake](https://firedrakeproject.org/), and [fluidity](http://fluidityproject.github.io/) testing as specific examples in learning materials, in particular looking at handling large (in time, and in resources) test runs and handling different languages (Python, C++, Fortran)

## Learning prerequisites

* [Jenkins on Azure](https://docs.microsoft.com/en-us/azure/jenkins/)
* [Docker on Azure](https://azure.microsoft.com/en-us/services/kubernetes-service/docker/)
* [Jenkins with Docker](https://jenkins.io/doc/book/pipeline/docker/)
* [Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/index?view=azure-devops)
