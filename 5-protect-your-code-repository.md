# 5. Protect your code repository

## Introduction

Your code is only as secure as the systems used to create it. As the central point at which your code is stored and managed, it's crucial that the repository is sufficiently secure.

Loss or compromise of access credentials, or breach of the underlying service, may allow attackers to modify your code base without your knowledge or permission.

Version control, peer review and built-in auditing are some of the advantages which come with using a code repository. If proper attention is paid to security measures, the benefits of using a repository far outweigh the risks.


### Actions

* **Choose a repository you trust**  
    Consider how the repository itself is administered and managed, including the underlying infrastructure. If the security of these components is compromised, it is difficult to assert trust in the code you store on it. If the repository is managed by a service provider, consider it against the NCSC [Cloud Security Principles](https://www.ncsc.gov.uk/guidance/cloud-security-collection). Layering a process of cryptographic signing and verifying code on top of the repository can help to increase confidence that the code has not been tampered with.

* **Consider the exposure of your repository**  
    Technically enforce a model of least privilege for who can make changes to your code repository.  Make sure all activity is attributable.

* **Protect access credentials**  
    User access to repositories is often authenticated using credentials, such as passwords or private keys. Loss of these credentials may allow an attacker to gain unauthorised access. Ensure that developers are encouraged to protect these credentials while they are used and managed within your development environment. Private keys should be password protected. Backing them onto a hardware token such as a [FIDO](https://fidoalliance.org/specifications/overview/) U2F Security Key makes them harder to abuse. Consider the option of rotating access keys.

* **Separate secret credentials from source code**  
    Logically separating secret credentials from source code and having a carefully defined injection process will help prevent them from getting leaked. Consider additional proactive controls such as key rotation and automatic scanning of your code repositories for secret keys to provide additional confidence.

* **Access to the repository should be revoked swiftly when no longer required, or in the event of compromise**  
    As your team evolves over time it's crucial you stay on top of who should have access and who should not.

* **When making code open, carefully consider whether any parts should remain confidential**  
    Although open-sourcing of code provides many benefits, it may also have a security impact. For example, code used to detect attacks would be of particular benefit to an adversary wishing to evade such measures. Attackers may also be able to glean information useful in formulating a spear-phishing attack. Some of your code may be more appropriately stored in a private repository.

* **Include open code in your risk model**
    Some of your code may be more appropriatly stored in a private repository. For example, code used to detect fraud attacks would be of particular benefit to an adversary wishing to avaid such measures. When coding in the open, there a number of security best practices you can adopt, like automated testing and peer reveiws.

* **Review all code changes**  
    Certain code repositories or branches will hold the source code from which production deployments are made. Ensure that all code merged into this master version has gone through a review process to help prevent unintended or malicious code being included.

* **External code changes may be malicious**  
    When coding in the open, an attacker may attempt to change or influence your code. Carefully review any change or pull requests to understand security implications, noting that attacks could be subtle or disguised. Take extra care if any of this code is automatically run in your build and test infrastructure, as it could be malicious.

* **If using a publicly accessible repository, take care of your identity**  
    The information stored in your online profile could be helpful in the formulation of spear-phishing, and other attacks.

* **Ensure your code is backed up**  
    Back up your code so it can be restored if anything bad happens to your repository.
    

## Self assessment

These examples are intended to help you assess your own practices, and those of your suppliers. The list below is not exhaustive.

| BAD | GOOD |
|-----|------|
| Developer devices that access the code repository are insecure, putting the code repository access keys at heightened risk of being stolen. | Developers make use of two factor authentication when accessing the code repository. |
| Any developer with access to the repository can modify and change the master version of the code without review or challenge. | Developers sign their code changes before being checked-in to the code repository, allowing for later verification. |
| Code used to detect cyber compromise is published on a public code repository, giving attackers the ability to inspect how it works. |The code repository service chosen was given careful consideration (e.g. using the [Cloud Security Principles](https://www.ncsc.gov.uk/guidance/cloud-security-collection) to understand the risks of different options). |
| Your code repository, hosted as a cloud service, adheres to bad security practices. | All code is reviewed before it is merged into the master version of the code repository. Extra care is taken if these code changes were submitted by an individual outside the development team. |
| Leavers' accounts and permissions are not deleted or revoked. | Access to source code repositories is joined up with the leavers and joiners process of your organisation. |
| Public profiles of key developers contain a large amount of personal information which could be used by an attacker to mount a convincing spear-phishing attack. | The accounts that developers use to access and modify your organisation's source code are periodically reviewed to assess potential risk. For example, through the public information available to an attacker and the security settings that are used on the accounts. |


## Related advice

* [The Cloud Security Principles](https://www.ncsc.gov.uk/guidance/cloud-security-collection)
* [A horror story of not protecting your repository](https://mikegerwitz.com/papers/git-horror-story)
* [Removing sensitive data from a repository](https://help.github.com/articles/removing-sensitive-data-from-a-repository/)
