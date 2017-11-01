# Principles of secure development & deployment

> 8 Principles to help you improve and evaluate your development practices, or those of your suppliers.

> ALPHA: This document is an initial draft. Due to the nature of the guidance, it seemed appropriate to share this on GitHub. We welcome your feedback through issues and pull requests. Please [read our blog](https://www.ncsc.gov.uk/blog-post/secure-development-and-deployment) that introduces this content.

![](images/lego.png)


## Introduction

Having a secure approach to development has never been so important.

The way we build software and systems is rapidly evolving, becoming more and more automated and integrated. Today, developers can define an entire system architecture in code and tie it to tooling which will automate both testing and deployment.

Thanks in large part to the arrival of cloud computing and 'infrastructure as code', systems of almost any size and complexity can be called into life, changed or terminated without leaving the desktop. On top of these new capabilities a process of quick and regular deployments has evolved. Often referred to as Continuous Delivery, this iterative approach is powerful, flexible and efficient.

But, these strengths bring with them a new set of risks which your security practices must address. To do so, you will need to consider security as a primary concern throughout the development and deployment process. If you do, the systems, features and fixes you build are less likely to be undermined by security compromise.

### What does this guidance do?

This guidance will help you understand the security implications of modern code development and deployment practices. The principles outlined here are primarily discussed in terms of digital services, but they are sufficiently high level that anyone building software which needs to remain secure will find them useful.

The Continuous Delivery approach to writing code introduces new risks, but it also brings a suite of tools for managing risk in the development process: version control, peer review, automated testing. Proper use of these tools can and should lead to increased security in your development practice. This guidance will help you understand how and where to apply these technologies.

IT systems rarely stand still, they change over time. With that in mind, these principles are not intended to be applied once and forgotten. They should be used to help build an environment which continually evaluates your systems as they evolve.

### Who is this guidance for?

The simple answer is everyone involved in software development and procurement. These principles are intended to help secure the entire process of software development, from establishing a security-friendly culture in your organisation, through to implementation and ongoing management. Whether you're securing a digital service or a traditional application, these criteria will help you gauge the security maturity of your own, or a supplier's development team, and the products and services you are producing or procuring.

Using these principles does not guarantee a secure product, but should help you gain confidence that the code you deploy is free from malicious interference and fits with your [buisness risk managment stratagy](https://www.ncsc.gov.uk/blog-post/coming-soon-new-guidance-risk-management-cyber-security). It is also not intended as a list of compliance standards - relevant parts may be pragmatically selected and used at your discretion.

> If you're developing a product that handles particularly sensitive information (eg information classified at SECRET or TOP SECRET), you should seek additional specialist advice about the specific threats you need to consider.

### Technical capacity

This is not in-depth guidance on how to avoid implementation vulnerabilities in the code you write. These are high level principles, intended to help teams responsible for creating IT systems manage their processes securely. The goal is to establish a set of working practices which foster security but also make code generally more stable and easy to maintain.

### Security is continuous

Development teams, technologies and good practices evolve over time, so you should re-visit your assessment periodically for it to remain meaningful.


## 8 Principles of Secure Development & Deployment

### 1. Secure development is everyone's concern
Everyone should accept that the security of IT systems is important. Even the most amazing application, delivered on time and to budget, is likely to have security vulnerabilities. A culture which values and rewards the detection and mitigation of these vulnerabilities is the most efficient and effective way to manage this 'fact of life'. Everyone building and running a service has a responsibility for security.

[Read more](1-secure-development-is-everyones-concern.md)

### 2. Keep your security knowledge sharp
Without a practical knowledge and understanding of secure development techniques, the code you produce is unlikely to be capable of withstanding attack. Give your developers and delivery team the time and resources necessary to form a good understanding of defensive code development and the risks to the systems they are building.

[Read more](2-keep-your-security-knowledge-sharp.md)

### 3. Produce clean & maintainable code
Complexity is the enemy of security. Code should be developed in line with good practice, so it can be extended and maintained effectively. Clean, well documented code is more efficient and easier to develop. It will also be easier to secure. Third party code libraries or other code dependencies need to be considered in the same light as the code you author.

[Read more](3-produce-clean-and-maintainable-code.md)

### 4. Secure your development environment
If your development environment is insecure, it's difficult to have confidence in the security of the code which comes from it. These environments need to be suitably secure, but should also facilitate and not impede the development process. Fortunately, it is possible to provide a solution that is both secure and usable by developers.

[Read more](4-secure-your-development-environment.md)

### 5. Protect your code repository
As a central point from which your code is stored and managed, it's crucial that the repository is sufficiently secured. Loss or compromise of access credentials, or breach of the underlying service may allow attackers to modify your codebase without your knowledge. However, if proper security measures are taken, the benefits of using a code repository service far outweigh the risks.

[Read more](5-protect-your-code-repository.md)

### 6. Secure the build and deployment pipeline
There are huge efficiency savings to be had from automating functions such as building code, running tests and deploying reference environments. However, these processes are security critical. Take care to ensure that your build and deployment tooling cannot undermine the integrity of your code, and that key security processes cannot be bypassed before changes are pushed to your customers.

[Read more](6-secure-the-build-and-deployment-pipeline.md)

### 7. Continually test your security
Performing security testing is critical in detecting and fixing security vulnerabilities. However, it should not get in the way of continuous delivery. Automating security testing where possible provides you with easily repeatable, scalable security measures. Your specialist security people can then concentrate on finding subtle and uncommon weaknesses.

[Read more](7-continually-test-your-security.md)

### 8. Plan for security flaws
All code is susceptible to bugs and security vulnerabilities. This is a fact of life. Accept that your code will have exploitable shortcomings and establish a process for capturing and managing them from identification through to the release of a fix. Keep track of your security debt by tracking issues with a register from identification to mitigation.

[Read more](8-plan-for-security-flaws.md)
