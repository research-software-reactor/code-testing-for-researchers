# Opening up cloud CI for researchers

Effective testing is critical for research software projects. During development, good testing practise helps to quickly identify software problems and maintain code quality. When software is operational, ongoing testing ensures that any changes to the software do not break required scientific functionality. Building and testing in a precisely specified environment ensures reliability and reproduceability.

Cloud resources are often key to good testing, either in the form of hosted CI solutions such as Azure pipelines or through access to on-demand resources for infrequent resource-intensive test runs where full-time dedicated hardware would be prohibitively expensive.

But a research software project developed and maintained by an individual scientist or small research group may struggle to implement effective automated testing. Hosted testing such as Azure pipelines or Travis CI are aimed at applications developers and often poorly suited to research software. But scientific programmers are generally not systems administrators and have neither time nor inclination to learn the background skills needed to run a custom testing platform -- they are focused on the science, not the infrastructure.

Specific examples of this would be:

* Research software that is tested by running cut-down versions of real world problems, but still require an order of magnitude more resources than available on a standard hosted CI worker node
* Test platforms that require software to be containerised, but none of the researchers are aware of what containers are or how to implement them beyond basic methods
* Learning materials for deploying custom testing platforms which assume basic devops/syadmin background and are sufficiently opaque to researchers that they do not make use of them
* Test platforms hosted on kubernetes where researchers are unaware of kubernetes and are put off by the added layer of learning needed to maintain the service

Requiring an individual or small research group to set up and maintain a custom testing platform is generally an inefficient use of their time, and improving hosted CI provision to cater for research software needs is a far more sensible route to take. In the case where researchers have a reasonable level of sysadmin knowledge to the point they can reasonably deploy and maintain a custom testing platform (ie, Jenkins on AKS) they hit problems arising from the differences between standard applications and research software. For example:

* Large projects lean heavily on github, which temporarily disables their access due to overuse
* Effective testing needs a variety of vm types, and AKS only supports a single nodepool per cluster
* Research software containers can be very large and hence difficult to handle in cost- and time-efficient ways
* Documentation tends to be written assuming application deployment, not research software development

## Sprint objectives

* Identify areas where Azure Pipelines could be improved to support research software needs
* Identify shortfalls in AKS which would improve AKS+Jenkins for research software
* Use devito, firedrake, and fluidity testing as specific examples in learning materials

## Learning prerequisites

* [Jenkins on Azure](https://docs.microsoft.com/en-us/azure/jenkins/)
* [Docker on Azure](https://azure.microsoft.com/en-us/services/kubernetes-service/docker/)
* [Jenkins with Docker](https://jenkins.io/doc/book/pipeline/docker/)
* [Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/index?view=azure-devops)
