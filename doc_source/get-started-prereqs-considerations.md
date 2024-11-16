# Prerequisites and considerations -- to -- set up IAM Identity Center<a name="get-started-prereqs-considerations"></a>

**Topics**
+ [Are you new to AWS?](#get-started-newuser)
+ [Prerequisites and considerations for specific environments](#additional-prerequisites-considerations)

## Are you new to AWS?<a name="get-started-newuser"></a>

* if you do NOT have an AWS account -> [sign up for one](https://docs.aws.amazon.com/accounts/latest/reference/welcome-first-time-user.html#getting-started)
* proceed to [Step 1: Enable IAM Identity Center](get-started-enable-identity-center.md)\. 

## Prerequisites and considerations -- for -- setting up IAM Identity Center | specific environments<a name="additional-prerequisites-considerations"></a>

**Topics**
+ [Active Directory or an external IdP](#prereqs-active-directory-idp-identity-source)
+ [AWS Organizations](#prereqs-organizations)
+ [IAM roles](#prereqs-iam-roles)
+ [Next\-generation firewalls and secure web gateways](#prereqs-next-generation-firewalls-secure-web-gateways)

### Active Directory or an external IdP<a name="prereqs-active-directory-idp-identity-source"></a>

* if you're ALREADY managing users & groups | Active Directory or an external IdP -> 👀connect this identity source | (enable IAM Identity Center & BEFORE you create users and groups ) 👀  
* requirements to use Active Directory
  + have 1 EXISTING / time | (AWS Directory Service & AWS Organizations management account)
    + AD Connector or
    + AWS Managed Microsoft AD directory
  + if you need to support >1 domains or forests -> use AWS Managed Microsoft AD
    + see:
      + [Connect a directory in AWS Managed Microsoft AD to IAM Identity Center](connectawsad.md)
      + [Connect a self\-managed directory in Active Directory to IAM Identity Center](connectonpremad.md)
  + if you use AWS Managed Microsoft AD -> enable IAM Identity Center | AWS Region == AWS Managed Microsoft AD directory is set up
    + -> AWS access portal URL == your directory URL

### AWS Organizations<a name="prereqs-organizations"></a>

* 👀AWS account -- MUST be managed by -- AWS Organizations👀
  * if you have NOT set up an organization -> choose it | enable IAM Identity Center
  * if you've ALREADY set up AWS Organizations -> make sure that ALL features are enabled
    * see [Enabling All Features | Your Organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_support-all-features.html)

* requirements to enable IAM Identity Center
  * sign in to the AWS Management Console -- via your -- AWS Organizations management account's credentials
    * NOT possible -- via -- AWS Organizations member account's credentials
    * see [Creating and Managing an AWS Organization](http://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org.html)

### IAM roles<a name="prereqs-iam-roles"></a>

* check whether your account -- is approaching the -- quota for IAM roles
  * see [IAM object quotas](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_iam-quotas.html#reference_iam-quotas-entities) 
  * recommendations
    * 👀if you're close to the quota limit -> request a quota increase 👀 
      * Reason: 🧠you might experience problems with IAM Identity Center | provision permission sets to accounts 🧠

### Next\-generation firewalls & secure web gateways<a name="prereqs-next-generation-firewalls-secure-web-gateways"></a>

* if you filter access to specific AWS domains or URL endpoints -- via a -- web content filtering solution (_Example:_ NGFWs or SWGs) -> 👀add the following domains or URL endpoints | your web-content filtering solution allow-lists👀
  * -> 👀enables IAM Identity Center to function correctly 👀
  * Specific DNS domains
    + \*\.awsapps\.com \(http://awsapps\.com/\)
    + \*\.signin\.aws
  * Specific URL endpoints
    + https://*\[yourdirectory\]*\.awsapps\.com/start
    + https://*\[yourdirectory\]*\.awsapps\.com/login
    + https://*\[yourregion\]*\.signin\.aws/platform/login