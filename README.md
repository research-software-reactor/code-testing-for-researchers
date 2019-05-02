# Opening up customised cloud testing for researchers

Research software needs to be tested effectively. When bugs are introduced during development, testing helps quickly identify them and prevent them becoming long-term, difficult to identify issues. Good testing helps to automatically check code quality against established standards. Once software becomes operational, users can supply tests that are run against any changes to the software, helping developers ensure they don't break scientific functionality during updates. And running builds and tests in a standardised environment gives guarantees of reliability and reproduceability.

Some research software remains untested, often due to researchers not having the time or inclination to learn technical skills needed for setting up testing services. Some research software is tested, but only on local computers maintained by the research team. In most research groups, using researcher time to run technical services is very inefficient; staff have a high level of scientific programming skill and interest, but generally have little background or interest in technical systems needed to set up and maintain a testing service and its associated hardware.

For smaller research software projects, using a cloud-hosted testing platform such as [Azure pipelines](https://azure.microsoft.com/en-us/services/devops/pipelines/) may be a good solution. This is a well-established method, well documented, and with good availability of templates for configuration files. However, for many research software projects it may quickly become restrictive, and researchers looking to use such a platform should be aware of the limitations before committing too much time and effort into it. In particular, where research software needs to run larger, operationally realistic problems, the standard testing hardware provided may be too slow to complete the test within allowed time limits, or may run out of resources to run the test at all.

For larger research software projects, custom testing is likely to be required. This opens up the possibility of running much larger tests on hardware that more closely resembles operational systems the software will use, perhaps through large numbers of cores, large memory, or provision of GPUs. It also opens up the potential for less frequent but long-running tests, and for archiving test environments and results to comply with reproduceability requirements. However, traditionally this has meant taking researcher time away from scientific programming and into technical learning and administration, which is generally neither desirable nor efficient.

Identifying key requirements of testing research software and generating learning materials for a research group to quickly and efficiently set up and maintain testing would be very high value, freeing up high-value scientific programming time.

## Sprint objectives

Suggested learning materials to develop are:

* Understanding the requirements of research software testing in terms of hardware resources, time, and data volume, so quick and accurate judgements can be made by researchers as to the suitability of hosted testing platforms
* Identifying efficient solutions to give low-maintenance but capable custom testing platforms that can be simply replaced if they go wrong, rather than needing time and technical skills to fix
* Identifying commonly recommended testing platforms that look interesting but are likely to end up being high cost in terms of researcher time or have inobvious issues that will cause problems for research software testing
* Spotlighting common problems that research software testing may encounter, so researchers are primed to quickly identify and fix them if and when they occur, without having to invest valuable time in debugging
* Lay out clearly and concisely cost considerations with using cloud resources for research software testing, helping researchers to quickly get to grips with the balance between time and cost whilst writing test configurations
* Provide a set of clear, templated examples of research software using [container images](https://www.docker.com/resources/what-container) for standardising and archiving environments and test output; this could use [devito](http://www.opesci.org/devito/index.html), [firedrake](https://firedrakeproject.org/), and [fluidity](http://fluidityproject.github.io/) testing as specific examples, covering handling large (in time, and in resources) test runs and handling different languages (Python, C++, Fortran).

## Learning prerequisites

* [Jenkins on Azure](https://docs.microsoft.com/en-us/azure/jenkins/)
* [Jenkins with Docker](https://jenkins.io/doc/book/pipeline/docker/)
* [Azure Pipelines](https://docs.microsoft.com/en-us/azure/devops/pipelines/index?view=azure-devops)
