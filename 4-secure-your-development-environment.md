# 4. Secure your development environment

## Introduction

There is sometimes a perceived conflict between security and usability. This situation is highlighted in the case of end user devices and the environments used to support software development.

Traditional enterprise IT is often configured to prevent users from running arbitrary code (and for good reason). However, some developers will require a less constrained environment, one which allows them to install relevant tooling and test their software effectively. Such flexibility can expose a broad attack surface to would-be attackers. This can make security professionals uncomfortable.

Developers tend to be technically smart. They will find 'clever' ways to work around hindrances, if that's what it takes to get their job done. We need a situation which is both flexible and secure. This guidance outlines how you can achieve this.

### Flexible _and_ secure

Securing your development environment is _not_ about preventing your developers from working. It's about understanding the risks to your environments, applying technical controls _where appropriate_ and being in a position to trust and verify legitimate usage.

The logical line between development and operations is becoming blurry. In environments where products and services are deployed through code, maintenance or operational activities can be carried out via configuration and software changes. The same individuals may often both develop and operate a service.

Where this is the case, it's important to recognise the onward impact that a compromised device may have on your services, and apply controls to help limit this exposure.

### Security gained

By performing the functions outlined in subsequent sections, you can help reduce the risk of an attacker:

*   stealing sensitive information (such as encryption and access keys, passwords or knowledge of security controls)
*   embedding malicious code in your project without your knowledge
*   using a compromised development device as a proxy to further attack your build and deployment pipeline, through to production
*   stealing code for the intellectual property it contains, or to release it publicly, causing embarrassment or degrading your security
*   understanding how your sensitive applications work - a first step in the planning of an attack

### Securing a flexible system

To do their job effectively, developers often need administration or root level permissions on their working environment.

However, providing this kind of flexibility can entail a bigger impact if malware compromises their device. There are numerous ways this can happen, including spear-phishing, drive-by downloads, or accidental malware installation.

The following measures can help you to understand and reduce these risks:

* **Separate business and development functions**

  Core business services such as email and document management often contain sensitive and highly prized information about your organisation and customers. If an attacker is able to compromise your development environment, they may try to pivot from this position to obtain additional benefit from their attack. Logically separating your development environment from other functions makes pivoting more difficult.

  Separation can be achieved without resorting to physically different devices. For example, a user may 'browse down' from a protected environment that is more locked down, into a local virtual machine or a remote environment where they can carry out development functions in a more flexible environment.

* **Consider your development environment compromised**

  If an attacker is able to compromise a developer's environment they will inherit the same level of permissions and access as that developer. Placing additional controls between your developer environments and critical systems will help to reduce this impact.

  For example, the use of multi-factor authentication will make it harder for an attacker who has compromised a device to leverage stolen keys, credentials and access tokens. Automated security testing and a multi-person review process as part of your deployment pipeline can help catch and prevent onward impact.

* **Trust your developers, verify their actions**

  People are not the weakest link, they are the first line of defence. Security-savvy individuals can sometimes be better at detecting and preventing attacks than technical controls.

  Trust can be placed in individuals who are security aware and strive to do the right thing. Investing in monitoring and auditing controls will help you to verify this is happening. Examples include network monitoring to detect suspicious activity, checking patch levels and verifying software that users are installing.


## Actions

* **Provide developers with the tools and environment they need**  
  Practical tooling is essential if you want to avoid technically savvy developers finding insecure workarounds. This may sometimes mean being a bit more tolerant to the risks of a developer device being compromised and putting wider protections in place to account for this. If an IT department can respond effectivley to software requests, it may be possible to avoid giving out local administrative permissions.

* **Trust your developers, verify their actions**  
  Educate users and trust them to do the right thing. Implement functions to verify their activity, and to detect suspicious activity or potential compromise.

* **Reduce the attack surface of your developer environment**  
  Apply the [NCSC end user device guidance](https://www.ncsc.gov.uk/guidance/end-user-device-security) to your development environment. Be pragmatic in the selection of your security controls so that you don't hinder development. Consider the security mitigation technology provided by devices and operating systems when selecting your devices and environments.

* **Protect access credentials and secret keys**  
  Carefully consider how you store and handle credentials that grant access to critical services and systems. Using multi-factor authentication will mean that stolen passwords are not sufficient on their own to gain unauthorised access. Use a least privilege access model and revoke any credentials which may have been compromised, or are no longer needed.

* **Assess the impact of a compromise and apply onward controls**  
  In the event a development environment is compromised, consider the onward technical controls that will protect the products and services you produce and publish.

* **Don't operate your production systems from a development environment**  
  Managing production ('live') services from development environments can be high risk. In situations where this is required, try to limit the exposure of your production services. Consider models for [least privileged](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material) access management and temporary access credentials through a request process. System [managment interfaces](https://www.ncsc.gov.uk/blog-post/protect-your-management-interfaces) are important to secure, but out of scope for this guidance.

* **Apply network architecture controls**  
  In the event that developer devices are compromised, constrain their onward access with wider network architecture controls that supports defence in depth. Examples may include firewall rule sets only permitting developer devices to communicate to intended services. Also consider the impact these services have on your developers. For example, non transparent proxies can hinder use of some technologies.

* **Carry out protective monitoring of your development environment**  
  You should have an idea of what legitimate use of your environment looks like. Combining this knowledge with logging from your environment can help to detect illegitimate use or potentially, a compromise. For example, are strange websites being accessed and are priviledged actions being carried out during unusual hours of the day?


## Self assessment

These examples are intended to help you assess your own practices, and those of your suppliers. The list below is not exhaustive.

| BAD | GOOD |
|-----|------|
| Production systems have good security, but the environment where code is built and deployed is a 'free for all'. | Staff are issued with securely managed devices, configured to protect them from a number of cyber security risks. |
| Any user or device with access to the development environment is able to make code and deployment changes and push these to production. There are no additional protections in place. | Developers are provided with the tools they need by connecting to a development environment, separated from the base device. Alternatively, developers don't need local admin because the IT Department responds quickly to their requests for development tools. |
| No protective monitoring, logging or auditing is carried out on development environments to help identify if and when a compromise occurs. | Instead of locking down developer devices, a trust and verify approach is used to reduce the risk of them being compromised. Owners are educated about the risks and asked to carry out security functions such as disk encryption, keeping software up to date and running antivirus. Monitoring controls are used to verify these are in place. |
| Developers are able to directly access production infrastructure from developer machines. There are no additional protections in  place, such as a change authorisation process, or controls that only allow 'secure' device access. | The risk of secret credentials being lost or stolen is reduced by pairing their use with two factor authentication.
| --- | The development environment has protective monitoring controls in place to help detect compromise and facilitate quick and effective remediation. |


## Related advice

* [End User Device Guidance](https://www.ncsc.gov.uk/guidance/end-user-device-security)
* [https://www.ncsc.gov.uk/blog-post/protect-your-management-interfaces](https://www.ncsc.gov.uk/blog-post/protect-your-management-interfaces)
* [https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material](https://docs.microsoft.com/en-us/windows-server/identity/securing-privileged-access/securing-privileged-access-reference-material)
