# 3. Produce clean & maintainable code

## Introduction

If your code lacks consistency, is poorly laid out and undocumented, you're adding to the overall complexity of your system. This is a problem for security because complexity hides bugs, some of which may result in security vulnerabilities.

An attacker only needs to find one way into your system. As the defender, you must try to find and mitigate them all. This task gets harder as your codebase grows in size and complexity, but you can minimise this effect by writing clean code.

If you created a flow graph of your code components, would it resemble a clean London underground tube map, or a complex mashup of spaghetti lines? The former is the goal.

A well thought out software architecture and consistent coding style will help your code base to be readable and maintainable. Code should be written in such a way that it is self documenting. Supplementary material, which is simple to understand, should be maintained alongside the system as it evolves.

Documenting a specification before writing code can help to reduce the complexity of the code itself, and a machine-readable specification can even be used to check the correctness of code automatically.

### Sources of complexity

Understand the sources of complexity and try to avoid them:

*   unstructured software architectures
*   vague naming of coding primitives such as classes, methods, functions and variables
*   confusing file naming conventions and folder structures
*   inconsistent code layouts and styles developing as contributors use their own individual styles and conventions
*   lack of additional supporting documentation (for example inline code comments, specifications, or system design documentation)
*   writing code without thinking about how it can be tested or checked for correctness

Having well-defined coding standards and a culture that enforces them means that a readable and logical code base can be maintained as your system develops.

Writing defensive code will be easier to achieve, security mistakes easier to spot, and issues, once identified, will be easier to fix. Following the advice outlined in this document will provide benefits that are not limited to security.

### Peer-reviewing code

Having two or more people review code will increase your confidence in the quality and security of your product before release. This process should be enforced within your deployment pipeline to help reduce the likelihood of damaging code changes being pushed to your production environment.

Any issues identified should be followed through with a fix. Remember, individuals can also peer review their own code, which can often save time before another person looks over it.

When reviewing code, you should consider:

* **Who performs the review?**  
  Does the person performing the code review have the correct security skills and knowledge of the system?

* **What is being reviewed?**  
  Try to avoid parts of your code being missed during review. It's easy to overlook issues in a large code base. This can be achieved by using small and regular code commits with comments or supporting analysis tools. Following a checklist of things to look for may help.

* **How are reviewers incentivised?**  
  Is the reviewer given the time to perform a meaningful review, or is there pressure to meet release deadlines? Is the reviewer blamed when issues are found that delay a release?

### External dependencies

The code that you write often only makes up a small fraction of the total code base that represents your system. Third party coding frameworks and libraries also need to be considered in the same light as the code you author. If third party components are themselves vulnerable, this is likely to also impact your system.

There is no easy way to mitigate the risks of third party code, but asking these questions may help:

*   If there is a security vulnerability in the third party components of your code, what security impact may this have on your system?
*   Is the dependency actively developed and maintained? If a vulnerability is found, who will fix it?
*   Are you using any old versions of third party code known to contain security vulnerabilities?
*   Do you know anything about the author and maintainer of the dependency? How do they view and approach security?
*   Does the dependency have any history of security vulnerabilities? What's important here is not necessarily that issues are discovered, but how they are handled.
*   If third party code is dynamically included into your product during the build or deployment process, can you ensure that it can't be maliciously modified? You could achieve this by verifying its origin and integrity, for example.
*   If the third party dependency you are using is configurable, consider disabling or removing unneeded functionality which may widen the attack surface of your product.

## Actions

* **Logically architect the layout of the code**  
  Writing clean and maintainable code is much easier when it's clear which components belong where. The architecture should take into account potential expansion. The [SOLID](https://en.wikipedia.org/wiki/SOLID_(object-oriented_design)) principles provide an example of this approach.

* **Coding standards** 
  Follow secure coding standards where available. For example, the [CERT Secure Coding project](https://www.securecoding.cert.org/) includes numerous rules for different languages to avoid potential security vulnerabilities.

* **Use self-explanatory naming conventions** 
  To help the reader understand what is going on, classes, methods, functions, file names and folder names should all be self-explanatory

* **Provide good supportive tooling to developers** 
  This may include modern IDEs with plugins that support the developer with capabilities such as pre-defined code snippets, debugging, unit testing, security hints, 'linting', specification checking and annotations.

* **Maintain a consistent coding style** 
  Understanding code becomes more difficult when different coding styles used by different developers mix and intertwine.

* **Clearly outline code block responsibilities**  
  Security issues can arise when one code component inaccurately assumes another has taken responsibility for an action. For example, when validating potentially malicious input at the border of your application. One way to achieve this is to have a comment block at the top of every method or function.

* **Separate secret credentials**  
  Keep secrets such as passwords and private keys logically isolated from the core code base. This will help prevent them being checked in to public code repositories. Hard coding credentials in source code is bad practice.

* **Do small and regular code commits**  
  Performing effective review becomes more difficult when large changes are made with each commit. Small and clearly labelled commits simplify the review and roll back process.

* **Attribute code changes to an author**  
  It should be clear who has authored a code change, and strong authentication controls should be used to do so. It should not be possible to falsify the code's author or its review status.

* **Police and critique each other's work through peer review**  
  Encourage a culture that does not accept complicated, confusing or insecure coding practices. Peer review helps prevent such issues being incorporated into your code base. Feedback helps support education within your team. Using pull requests and comments is one way to achieve this.

* **Team communications**  
  When multiple team members are working on the same code base, there should be strong and regular communication channels between them. The aim here is to avoid the following scenario: 'I thought you were securing that component!'. Keeping teams physical close to one-another, or providing real-time chat channels are two ways to achieve this.

* **Document and comment clearly and consistently**  
  Clear and concise documentation should support your product. This may be as a result of self-documenting code, code comments, or supportive material. Documentation should be kept up to date, as a system evolves. Old and out-of-date documentation is difficult to trust and could be damaging for security if it's interpreted incorrectly.

* **Support new team members**  
  Developers and other team members may come and go over the life span of a product. To ensure adequate knowledge of the product is maintained, provide good support and documentation to new team members. After all, who will fix security vulnerabilities left behind by previous developers?

* **Check return values and handle errors appropriately** 
  Checking for errors at the point of a call and handling them immedidately means that your code doesn't continue running in a potentially unstable state. This will make your code more robust and secure.



## Self assessment

These examples are intended to help you assess your own practices, and those of your suppliers. The list below is not exhaustive.

| BAD | GOOD |
|-----|------|
| No software architecture has been established and differing coding standards are used throughout the code base. | Coding standards are enforced by automated coding and style checking tools such as 'linting'. |
| Code commits cannot be attributed to a specific developer. | Code is stored in a version control system that has strong authentication controls regulating who can review and accept code changes. |
| Code commits are irregular, resulting in the changes being large and impractical to review. | There is a well thought out software architecture documented and the file and folder naming convention is self-explanatory, leading to logical code layout. |
| Code commit descriptions are confusing. | All developers create small, clear and well commented code commits on a regular basis. These are peer reviewed by other team members. |
| Code review is either non existent or ad-hoc. | New developers who do not conform to good practices have their code rejected. |
| Tests or specifications are missing. | Code is written with testing or correctness checking in mind.


## Related advice

*   [Agile Security](https://www.ncsc.gov.uk/blog-post/securing-agile-delivery-collaboration-crucial)
*   [EUD Security Guidance](https://www.ncsc.gov.uk/guidance/end-user-device-security)
*   [Digital Service Security](https://www.ncsc.gov.uk/guidance/security-design-principles-digital-services-main)
*   [Using TLS to protect data](https://www.ncsc.gov.uk/guidance/tls-external-facing-services)
*   [SEI CERT Coding Standards](https://www.securecoding.cert.org/confluence/display/seccode/SEI+CERT+Coding+Standards)
*   [OWASP Secure Coding Practices - Quick Reference Guide](https://www.owasp.org/index.php/OWASP_Secure_Coding_Practices_-_Quick_Reference_Guide)
*   [The Apple goto fail vulnerability: lessons learned](https://www.dwheeler.com/essays/apple-goto-fail.html)
*   [What does KISS stand for?](https://people.apache.org/~fhanik/kiss.html)
*   [CIS Security Controls (formerly SANS Top 20)](https://www.cisecurity.org/controls/)
