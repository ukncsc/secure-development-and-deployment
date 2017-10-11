# 2. Keep your security knowledge sharp

## Introduction

Creating code that is capable of withstanding attack requires an understanding of attack types and of defensive security practices. Your level of understanding in these areas must be regularly updated if it's to remain useful.

Fortunately, languages, frameworks and technology stacks often provide functionality to help us write 'good' code. These tools and features are regularly updated and improved, solving common issues while introducing new concepts. And that's the problem in a nutshell. Taking advantage of these new features (whether or not they are security related) requires an investment of time.

You can often avoid compromise by taking advantage of readily-available security features or techniques, but to do so you must know of their existence. You also need to understand how attackers work, and have the ability to discern the relevant feature or technique which will prevent a successful attack.

Teams armed with up to date information are much more likely to implement appropriate defensive controls in their code. At the very least they will know to seek specialist security input for unusual or particularly complex problems, _and_ for code that simply requires a higher level of confidence.


## Actions

* **Developers should be aware of common security threats to their code** 
  If they do not already have this knowledge, resources should be provided so that it can be gained. Examples may include standard injection techniques and handling [untrusted input](https://www.owasp.org/index.php/Injection_Theory).

* **Use your developer recruitment process to screen for basic security awareness** 
  Qualifications aren't the only way to establish this. Real world practical application is more important. If this isn't possible, allocate extra resources for security learning and development.

* **Make time and resources available for ongoing learning** 
  Invest in training to develop security knowledge and skills.

* **Teach developers about the types of threat their code will face** 
  This goal may be achieved through group workshops that assess attacks and threats to your systems.

* **Make developers accountable for the security of their code** 
  Most developers already take pride in their work - [security is everyone's concern](2-keep-your-security-knowledge-sharp.md).

* **Be aware and consider when there is a particular need to write code defensively** 
  Take extra time and care when implementing security critical components, writing your code defensively. For example, when validating input which may be attacker-controlled.

* **Get your security specialists to outline **for developers** which **components are** security-critical (this should not be 'everything')** 
  Developers should know when to seek extra support. Security efforts can then be prioritised.

* **Use established and well-tested security components instead of creating your own**  
  Many common problems (eg cryptography and data sanitisation) can be solved using existing solutions. This will save you the time and difficulty of validating your implementation as correct and error-tolerant.

* **Run sessions to learn from your mistakes, using real issues from your own product where possible**  
  Provide discussion and feedback on issues to improve future code commits.

* **Maintain a list of useful security training resources that are relevant for your product**  
  Developers with access to trusted information are more quickly able to read and apply it. Use trusted sources as [working code isn't always robust code](https://www.aisec.fraunhofer.de/content/dam/aisec/Dokumente/Publikationen/Studien_TechReports/englisch/stackoverflow.pdf).

* **Limit information available to attackers on public profiles**
  Be aware that information published on public profiles can be viewed by an attacker. Job roles, positions and personal details can be used to aid attacks such as spear-phishing.

*  **Keep up to date with security features in the tools, languages and other technologies you use**
  Compilers, IDEs and even languages evolve constantly. Often this will mean the addition of new security features, such as memory safe constructs in languages that are not inherently memory safe. But, technologies can also go out of date. In light of this, do not use [old, and deprecated APIs](https://cwe.mitre.org/data/definitions/676.html).


## Self assessment

These examples are intended to help you assess your own practices, and those of your suppliers. The list below is not exhaustive.

| BAD | GOOD |
|-----|------|
| Developers' knowledge of basic security considerations is not assessed during recruitment. | Every developer has a basic understanding of the security issues they need to look out for. |
| Developers do not think that security is their responsibility, relying on the security team to worry about it. | Developers with less experience in defensive coding carry out pair programming with more experienced partners. |
| Developers do not understand the basics of how coding flaws can be exploited, nor how to write defensively against such exploits. | Code is critiqued during review and shared with the wider team. |
| Time and resources to invest in security training are not available to developers. | When a security incident occurs, retrospective workshops are held where lessons are learned in a 'no blame' atmosphere. |
| Developers are too focused on delivery to invest in their security training. | Developers spend time keeping their security knowledge up to date. |
| There is no expertise available to answer security questions. | Individuals with security expertise are available and clearly visible to staff. |


## Related advice

* [Secure design principles](https://www.ncsc.gov.uk/guidance/security-design-principles-digital-services-main)
* [http://www.riscs.org.uk/wp-content/uploads/2015/12/Awareness-is-Only-the-First-Step.pdf](http://www.riscs.org.uk/wp-content/uploads/2015/12/Awareness-is-Only-the-First-Step.pdf)
