# What is IAM Identity Center?<a name="what-is"></a>

* == successor to AWS Single Sign-On /
  * 👁️expands the capabilities of AWS IAM 👁
  * == central place to admin 
    * users &
    * their access to
      * AWS accounts
      * cloud applications
  * term *single sign\-on* is STILL used -- throughout -- this guide

## IAM Identity Center features<a name="features"></a>

* **Workforce identities** or **workforce users** 
  * == Human users / are members of your organization
  * uses
    * across ALL your AWS accounts and applications
      * Reason: 🧠 main scope of AWS IAM Identity Center 🧠
  * ways to have
    * create workforce users and groups | IAM Identity Center or
    * connect and synchronize -- to an -- existing set of users and groups | your OWN identity source
      * supported identity source
        * Microsoft Active Directory Domain Services
        * external identity providers (_Example:_ Okta Universal Directory or Microsoft Azure AD)

* **Application assignments for SAML applications**  
  * allows
    * granting your workforce users in IAM Identity Center -- single sign\-on access to -- SAML 2\.0 applications (_Example:_ Salesforce and Microsoft 365)
      * -> NO need to set up separate federation

* **Identity Center enabled applications**  
  * some AWS applications and services -- discover and connect to -- IAM Identity Center 
    * _Example:_ Amazon Managed Grafana, Amazon Monitron, and Amazon SageMaker Studio Notebooks
    * -> 👁users have consistent
      * single sign\-on experience (to these applications) / NO additional configuration👁 
        * Reason: 🧠these AWS applications and services automatically receive 🧠
          * sign\-in
          * user directory services
      * experience | sharing application resources with others
        * Reason: 🧠applications share a common view of users, groups, and group membership 🧠 

* **Multi\-account permissions**  
  * allows
    * about IAM permissions / across multiple AWS | 1! time
      * planning for
      * centrally implementing
    * creating fine\-grained permissions / -- based on -- common job functions
    * defining custom permissions / meet your security needs
  * uses
    * assign those permissions -- to -- workforce users
      * == control their access | specific accounts

* **AWS access portal**  
  * == simple web portal
  * allows
    * workforce users -- can access with 1-click to -- ALL their assigned
      * AWS accounts
      * cloud applications

## IAM Identity Center rename<a name="renamed"></a>

* | July 26, 2022, AWS Single Sign-On -- was renamed to -- AWS IAM Identity Center
* table term comparison
    
    | **Legacy term** | **Current term** | 
    | --- | --- | 
    | AWS SSO user or SSO user | workforce user or user | 
    | AWS SSO user portal or user portal | AWS access portal | 
    | AWS SSO\-integrated applications | Identity Center enabled applications | 
    | AWS SSO directory | Identity Center directory | 
    | AWS SSO store or AWS SSO identity store | identity store used by IAM Identity Center | 

* table comparison for
  * applicable user,
  * developer reference
  * API reference

    | **Legacy guide** | **Current guide** | 
    | --- | --- | 
    | AWS Single Sign\-On User Guide | [IAM Identity Center User Guide](https://docs.aws.amazon.com/singlesignon/latest/userguide/what-is.html) | 
    | AWS Single Sign\-On SCIM Implementation Developer Guide | [IAM Identity Center SCIM Implementation Developer Guide](https://docs.aws.amazon.com/singlesignon/latest/developerguide/what-is-scim.html) | 
    | AWS Single Sign\-On API Reference Guide | [IAM Identity Center API Reference](https://docs.aws.amazon.com/singlesignon/latest/APIReference/welcome.html) | 
    | AWS Single Sign\-On Identity Store API Reference Guide | [Identity Store API Reference](https://docs.aws.amazon.com/singlesignon/latest/developerguide/what-is-scim.html) | 
    | AWS Single Sign\-On OIDC API Reference Guide | [IAM Identity Center OIDC API Reference](https://docs.aws.amazon.com/singlesignon/latest/OIDCAPIReference/Welcome.html) | 
    | AWS Single Sign\-On Portal API Reference Guide | [IAM Identity Center Portal API Reference](https://docs.aws.amazon.com/singlesignon/latest/PortalAPIReference/Welcome.html) | 

### Legacy namespaces / remain the same<a name="legacy-namespaces"></a>


* API namespaces
  * `sso`
  * `identitystore`
+ CLI commands
  + [https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-sso.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-sso.html)
  + [https://awscli.amazonaws.com/v2/documentation/api/latest/reference/identitystore/index.html](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/identitystore/index.html)
  + [https://awscli.amazonaws.com/v2/documentation/api/latest/reference/sso/index.html](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/sso/index.html)
  + [https://awscli.amazonaws.com/v2/documentation/api/latest/reference/sso-admin/index.html](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/sso-admin/index.html)
  + [https://awscli.amazonaws.com/v2/documentation/api/latest/reference/sso-oidc/index.html](https://awscli.amazonaws.com/v2/documentation/api/latest/reference/sso-oidc/index.html)
+ [Managed policies](https://docs.aws.amazon.com/singlesignon/latest/userguide/security-iam-awsmanpol.html) containing `AWSSSO` and `AWSIdentitySync` prefixes
+ [Service endpoints](https://docs.aws.amazon.com/general/latest/gr/sso.html#sso_region) containing `sso` and `identitystore`
+ [AWS CloudFormation](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/AWS_SSO.html) resources containing `AWS::SSO` prefixes
+ [Service\-linked role](https://docs.aws.amazon.com/singlesignon/latest/userguide/using-service-linked-roles.html#slr-permissions) containing `AWSServiceRoleForSSO`
+ Console URLs containing `sso` and `singlesignon`
+ Documentation URLs containing `singlesignon`