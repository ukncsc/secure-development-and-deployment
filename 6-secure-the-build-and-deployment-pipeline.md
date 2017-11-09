# 6. Secure the build and deployment pipeline

## Introduction

Continuous integration, delivery and deployment are modern approaches to the building, testing and deployment of IT systems.

Small, regular code commits can automatically trigger builds and run comprehensive testing. Whole system deployments can be made to development and reference environments, prior to deploying an identical production environment. The holy grail is a deployment pipeline that minimises the need for manual processes, allowing fully-tested regular production deployments in a matter of minutes.

The security of this process is critical if you need to protect the integrity of your code and the systems it builds. Security should, however, work with this process, not hinder it. Embrace '[DevSecOps](https://www.devsecops.org/)' approaches to gain confidence in your services.

_Although this principle is primarily aimed at digital services using continuous delivery practices, you may still find some of this content helpful if you're using a different delivery approach. Development of most products and services will have some version of a 'deployment pipeline'._


## Preliminary question: Do you trust the devices on which code is being written?

When considering build and deployment security there is an initial question you need to ask yourself before making any decisions: do you trust the devices on which the code is being written?

* **If you do:** the build and deployment pipeline needs to maintain the integrity of your code while it's being deployed. It can also be used to gain additional confidence in the security of your code.

* **If you do not:** the build and deployment pipeline becomes the point at which you need to gain confidence in the code you are deploying. This is critical. Your onward pipeline is the gateway to production.


## Actions

* **Use a pipeline you trust**
  Consider how the pipeline itself is administered and managed, including the underlying infrastructure. If the security of these components is compromised, it is difficult to assert trust in code you build and deploy through it. If the pipeline is managed by a service provider, use the NCSC [Cloud Security Principles](https://www.ncsc.gov.uk/guidance/cloud-security-collection) to understand the security properties of their service. Layering a process of cryptographic signing and code verification on top of your repository can help to increase confidence that the code has not been tampered with.

* **Peer review code before deployment**
  Accept or reject according to your development processes. This step is an important source of quality control, so you should implement technical controls to prevent it being bypassed.

* **Control how deployments are triggered**
  Code that triggers automated deployment to production environments should be carefully managed. Production deployments shouldn't be made from untrusted code repositories, forks or branches.

* **Run automatic testing as part of your deployments**
  Well thought out tests can help you gain confidence in the security of your code. Bad tests can get in the way. Where possible, automate testing so that it supports the deployment pipeline. 'Cheap' tests can be run on every code change, resource-intensive tests can be saved for notable releases. Don't ignore tests that fail. Re-evaluate and refactor testing that does not work for you.

* **Carefully manage secrets and credentials**
  Your deployment pipeline tooling may require secret tokens or credentials to launch and run code. Inadvertently exposing secrets may allow unauthorised access to your systems. Take care in how you store, manage and inject these into your environment. Consider rotating keys and how this process can be automated to make it practical in your workflow.

* **Ensure deployment pipeline controls cannot be bypassed, or re-ordered**
  All deployment processes should be followed from development through to deployment. This could be achieved architecturally, or by carrying out cryptographic signing and verification at each stage.

* **Avoid 'self policing'**
  The pipeline should enforce rules that define whether code is accepted or rejected before deployment. It's possible that these controls are themselves implemented in source code, along with your product. It should not be possible for individuals to 'police themselves' by modifying these rules.

* **Be cautious of untrusted branches and pull requests**
  Consider how your automated build and test tooling react to branches of your code or pull requests that may be malicious. For example, an attacker may be able to execute malicious code within your environment if your automated tooling runs over third party pull requests.

* **Be cautious of importing third party libraries and their updates**
  Ensure only intended dependencies are included and that they come from legitimate sources. Old versions of libraries may contain security vulnerabilities that will affect your own code. Keep in mind that if you import vulnerable code that it can make your system vulnerable too.

* **Consider hard breaks and approval (optional)**
  Fully automated deployment without adequate security controls in place is high risk. If you don't have confidence in the deployment pipeline processes, consider a hard break that requires approval before releases go live into a production environment.


## Self assessment

These examples are intended to help you assess your own practices, and those of your suppliers. The list below is not exhaustive.

| BAD | GOOD |
|-----|------|
| The underlying platform that your continuous integration tooling runs on is insecurely designed or configured. | A cloud service-provided, continuous integration platform is used after being assessed against the [cloud security principles](https://www.ncsc.gov.uk/guidance/cloud-security-collection). |
| Everyone in the development team can make changes to both the code base itself, and the deployment pipeline checks, without peer review. | When changes are made to critical deployment steps, the important nature of the change is recognised and carefully reviewed before being accepted. |
| A peer review process is followed between team members before code changes are made to the master branch. However, there are no technical controls in place preventing direct changes to the master branch. | Code is digitally signed and this signature is later used by the deployment pipeline to help ensure unauthorised changes have not been introduced. |
| External pull requests on the code repository are automatically run by integration tooling, allowing third parties to execute untrusted code in the test and development environment. | During the build process, only a whitelist of trusted third party repositories are permitted to be pulled from, and they are accessed in secure ways (e.g. using TLS). |
| During the build process, third party libraries are dynamically pulled in using insecure protocols such as HTTP. No technical controls are in place to help prevent malicious libraries being included. | The security controls in the deployment pipeline are assessed and implemented in such a way that they cannot be bypassed. |


## Related advice

* [https://www.devsecops.org/](https://www.devsecops.org/)
