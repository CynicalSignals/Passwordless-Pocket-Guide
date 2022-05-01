# The Pocket Guide for Passwordless Authentication in the Enterprise

This is a quick reference sheet to help jumpstart researching how passwordless authentication can help to improve your organization's security posture against cyber threats.

*Note: This guide was created for a research project as part of a graduate program at Wilmington University. This guide is provided under GNU General Public License v3.0. However, all referenced materials are provided as-is, without warranty, and are the sole responsibility of the original authors and licensing. Pull Requests and GitHub issues are welcome for all feedback and suggestions!*

### Definitions

| Word | Meaning |
|------|---------|
| User | The person logging in -- can be a client, customer, employee, consumer, etc. |
| System | The thing the User is logging in to -- can be an application, website, physical door entry, etc. |

## What is passwordless authentication?

Compared to passwords which are something a User must know and remember in their brain or "write down" (virtually or physically), passwordless authentication provides a way for Users to prove who they are without picking *and* remembering a secure password. Passwordless authentication comes in many forms and is often tied to something in a physical space that the User **is** or can **possess**. Passwordless authentication still uses the similar cryptographically sound methods that systems use for verifying passwords; however, it removes the burden from the User to have to pick solid and unique passwords while remembering them.

It is helpful to know the [Three Factors of Authentication](https://www.pearsonitcertification.com/articles/article.aspx?p=1718488) ([which have been expanded in recent years to four and five factors](https://dojowithrenan.medium.com/the-5-factors-of-authentication-bcb79d354c13)) to understand the difference between passwords (something you know) and passwordless (something you have or something you are).

#### Something you know

- This could be a passphrase, codeword, PIN, etc. These unique elements are intended to live solely in the user’s head (or written down). The system has mechanisms to validate whether the knowledge check was correct. This is one of the most common methods of authentication where a username (non-secret) is paired with a password (secret) to authenticate.

#### Something you have

- This is often tied to a physical object; however, the definition can extend to digital possession in some circumstances. This can be a digital key, smartphone, card, personal telephone number, email address, etc. These are things the User can possess to prove themselves, either by having logical control over something like SMS and email or by presenting physical possession of an object which utilizes cryptography as proof of ownership.

#### Something you are

- This applies to the user’s biological makeup related to unique physical attributes. Facial recognition, fingerprint readers, and retinal scans are examples of this.

### The passwordless experience

The FIDO Alliance has created an open standard to allow certified interoperability between systems and hardware, meaning anyone can implement passwordless authentication in their system: [https://fidoalliance.org/fido2/](https://fidoalliance.org/fido2/)

Organizations and vendors implementing passwordless authentication can make risk-based decisions to determine which specific passwordless authentication methods they support based on their environment and use-cases. Each option has varying degrees of upfront cost and initial support complexity. However, there is likely a solution that will work for any organization's unique situation. Where one organization may want to rely on physical security keys for access, others may choose biometrics or a smartphone app.

Using Microsoft as an example, there are [several methods available that organizations can choose to implement with different tradeoffs](https://docs.microsoft.com/en-us/azure/active-directory/authentication/concept-authentication-methods).

## Why should I implement passwordless authentication instead of continuing to use passwords everywhere in my environment?

Shifting away from the weaknesses of relying on "something you know" and depending more on "something you have/are" can offer increased security benefits while improving user experience.

### Passwords are cumbersome

- [Password fatigue. The average User has to remember or manage almost 80 passwords!](https://southernmarylandchronicle.com/2020/02/26/new-research-an-average-person-has-more-passwords-than-an-average-pop-song-has-words/)
- [....the average **business** User has over 190 passwords...!](https://www.securitymagazine.com/articles/88475-average-business-User-has-191-passwords)
- [....which costs businesses over $1 million a year in support costs...!](https://www.keepersecurity.com/assets/pdf/Keeper-White-Paper-Forrester-Report.pdf)

### Passwords have severe weaknesses

- [There many ways to attack passwords or trick the User into providing their credentials to an attacker.](https://www.sailpoint.com/identity-library/8-types-of-password-attacks/)
- [80% of breaches used stolen credentials.](https://www.verizon.com/business/resources/reports/dbir/2020/summary-of-findings/)
- [41% of breaches involving malware deployed password stealers.](https://www.verizon.com/business/resources/reports/dbir/2020/results-and-analysis/)
- [A User may have the most unique and secure password in the world for their work account. If they re-use it across more than one insecure service that gets hacked, that password is now exposed. You can't stop people from using the same password at home that they do at work.](https://haveibeenpwned.com/Passwords)
- [After implementing passwordless security keys for logins, Google reported detecting 0 employees (out of 85,000+) getting phished in 2017.](https://krebsonsecurity.com/2018/07/google-security-keys-neutralized-employee-phishing/)

## Which one of my vendors/products/things supports passwordless authentication?

While passwordless authentication is not a new concept, some systems do not yet support it. However, prominent identity and access space players have made significant efforts to adopt and offer passwordless authentication to their customers. It is best to reach out to your vendors directly for more information, especially since some vendors may lock security features behind different pricing tiers. Some references to the more popular solutions are below:

- [Azure Active Directory/Hybrid Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/authentication/howto-authentication-passwordless-deployment)
- [Google Workspace](https://workspace.google.com/learn-more/key_for_working_smarter_faster_and_more_securely.html)
- [Okta](https://www.okta.com/passwordless-authentication/)
- [Duo](https://duo.com/solutions/passwordless)
- [Ping Identity](https://docs.pingidentity.com/bundle/pingone/page/web1608657831832.html)
- [Auth0](https://auth0.com/blog/fido-security-key-support-comes-to-auth0/)

## What hurdles may I encounter with passwordless authentication, and how do I avoid them?

- [Some legacy systems will never support passwordless authentication directly. You may need to get creative with architecture and access controls that allow you to use passwordless authentication by abstracting direct access to something like a bastion host.](https://doubleoctopus.com/blog/digital-transformation/legacy-systems-passwordless-authentication/)
- [...and when you can't do that, be prepared to come up with hardening solutions where passwords will remain.](https://www.techtarget.com/searchsecurity/opinion/How-to-go-passwordless-if-not-all-your-apps-support-modern-authentication-standards)
- The benefits of passwordless authentication can far exceed passwords; however, it must be made clear it is not infallible and that each employee is responsible for making sure they are operating as securely as possible. Passwordless authentication is a technology built and used by humans which guarantees there are still weaknesses. Passwordless authentication is strictly an authentication technology and is not an adequate replacement for other security controls and best practices. It does lend itself to a hardened login experience. Still, an organization is only as strong as its weakest security control, so all other facets of a network, infrastructure, and application services must be appropriately secured. 
- You should still enforce [MFA](https://en.wikipedia.org/wiki/Multi-factor_authentication) where applicable.
- Passwordless can be a strange concept if you've been used to providing passwords. Users and support staff must be educated on how passwordless authentication functions regardless of which specific authentication method is selected. This includes covering the technology at the appropriate technical level for the audience, reviewing proper hygiene when using passwordless authentication, and ensuring the organization’s written policies are reiterated when applicable. 
- With many businesses still heavily relying on a remote workforce, a strategy must be developed to securely onboard new users into passwordless authentication systems. There will also need to be ways to facilitate disabling physical methods which may become lost or stolen and provide a means of recovery to reduce business impact while maintaining a high level of security.
- As passwords become less prevalent over time, attackers will begin to focus on gaining control over passwordless authentication methods, including but not limited to [social engineering support teams](https://securityboulevard.com/2021/04/how-social-engineering-tactics-can-crack-multi-factor-authentication/) by pretending to be the User or simply [paying Users to access their work accounts or work on behalf of them](https://krebsonsecurity.com/2021/08/wanted-disgruntled-employees-to-deploy-ransomware/) (insider threat). While these attacks are not exclusive to passwordless authentication, organizations should be prepared with compensating controls regardless of how their Users authenticate.
