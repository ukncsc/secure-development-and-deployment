# 8. Plan for security flaws

## Introduction

All but the very simplest software is likely to contain bugs, some of which may have a security impact. This is true of code written in-house as well as any [third-party resources on which your product relies](3-produce-clean-and-maintainable-code.md). Flaws are not limited to coding errors and implementation mistakes, they can include architectural and design issues too.

Having accepted the inevitability of such problems, make a plan to find and fix them.

### Security debt

When software is first developed, the priority is to establish value, to identify a [minimum viable product](https://en.wikipedia.org/wiki/Minimum_viable_product). Code robustness and security-related functionality are understandably traded out. This creates [technical debt](https://martinfowler.com/bliki/TechnicalDebt.html).

Some of this technical debt may have a security impact (for example, granting full administrative permissions to an application during development, instead of investigating which specific permissions are required for the application to function). We like to call this 'security debt'.

Keeping a register of these items as you go along is important. It will allow you to return and address them later. Consider how 'expensive' the [design decisions](https://www.ncsc.gov.uk/guidance/security-design-principles-digital-services-main) you make today will be later down the line.

## Guidance

* **Put [vulnerability management](https://www.ncsc.gov.uk/guidance/vulnerability-management) processes in place**  
  Where you use widely available software and hardware, you should be deploying patches and looking for known weak configurations.

* **Maintain a register of security debt accumulated during product development**  
  Security debt is often accumulated to meet business delivery. Maintaining a register allows you to track your cumulative debt and later address the issues as your product or service matures.

* **[Invest in security skills](2-keep-your-security-knowledge-sharp.md)**  
  A product team needs to be able to identify issues and get them fixed.

* **Perform root cause analysis**  
  After any event, carry out a [post-mortem](https://landing.google.com/sre/book/chapters/postmortem-culture.html) to help iterate your procedures and adapt your code. Sometimes it's possible to mitigate a whole class of vulnerabilities rather than having to do 'whack-a-mole' for each one. When possible, address the root cause. Seek out the point where the issue was introduced so you can learn from it.

* **Provide a way for others to disclose security flaws to you**  
  It should be possible for users and researchers to responsibly disclose security issues to you. This should be seen as a positive action - an attacker could have used the issue to do harm.

* **Feed findings back into the [testing process](7-continually-test-your-security.md)**  
  Creating security tests for issues identified helps to gain confidence they will not occur again.


## Self assessment

These examples are intended to help you assess your own practices, and those of your suppliers. The list below is not exhaustive.

| BAD | GOOD |
|-----|------|
| Once a product has been created there is no ongoing process in place for fixing security issues. | There is a clear vulnerability disclosure process that allows individuals to responsibly report security issues without backlash. |
| There is no 'front door' available for people to report security issues. | Discovered security issues are discussed by members of the development team so that the issue can be fixed and learned from. |
| System changes and staff churn leave no one with the knowledge or understanding needed to fix security issues in older parts of the system. | A regular feed of vulnerability information about the technologies and products you depend on is used to identify relevant new vulnerabilities. |
| Security issues are reported but not properly mitigated. | --- |
| Repeated security vulnerabilities of the same type keep happening and the root cause of the problem is not considered or addressed. | --- |
| Security practices of developed code are good but old versions of third party libraries with known vulnerabilities are still used. | --- |
