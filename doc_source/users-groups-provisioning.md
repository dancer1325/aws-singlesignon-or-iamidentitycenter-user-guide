# Users, groups, and provisioning<a name="users-groups-provisioning"></a>

* IAM Identity Center -- manages access to -- ALL your
  * AWS Organizations accounts,
  * Identity Center enabled applications,
  * OTHER business applications / support SAML 2.0 standard

## User name and email address uniqueness<a name="username-email-unique"></a>

* users MUST be UNIQUELY identifiable | IAM Identity Center
  * IAM Identity Center -- implements a -- user name / primary identifier for your users
* set user name = user’s email address
  * -- done by -- MOST people 
  * NOT required by
    * IAM Identity Center
    * SAML standard
  * uses
    * 👀unique user identifier | MOST of SAML-based applications 👀
      * got from assertions / SAML identity provider sends | authentication
* IAM Identity Center
  * requires that
    * ALL user names and email addresses / your users are 
      * NON-NULL
      * unique

## Groups<a name="groups-concept"></a>

* Groups
  * == logical combination of users / you define
  * allowed
    * create groups
    * add users | groups
  * NOT allowed -- by -- IAM Identity Center
    * nested groups
      * == add a group | group
  * uses
    * assign access | AWS
      * accounts
      * applications

## User and group provisioning<a name="user-group-provision"></a>

* users & groups / you can use
  * created | IAM Identity Center
  * EXISTING |
    * Active Directory
    * ANOTHER external identity provider
* Provisioning
  * := process of making user & group information -- available for use by -- IAM Identity Center & Identity Center enabled applications
    * allow
      * IAM Identity Center -- can assign -- users & groups access permissions | AWS account
      * Identity Center enabled applications -- can work with -- them
    * -- depend on the -- identity source / you use
      * see [Manage your identity source](manage-your-identity-source.md)