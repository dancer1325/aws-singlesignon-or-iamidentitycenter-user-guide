# Identity Center enabled applications<a name="app-enablement"></a>

* == applications /
  * -- ca be integrated by -- OTHER AWS
    * applications
    * services 
  * \+ IAM Identity Center
    * -- can --
      * perform authentication
        * -> 👀easy to give users | your workforce -- access to -- MANY applications | different AWS accounts👀
      * access information about users and groups
        * 👀== IAM Identity Center -- share the user & group information with -- Identity Center enabled applications 👀
        * _Example:_ user sign | application / generates performance dashboards for resources / user controls
          * the user might share the dashboard -- via -- looking up an IAM Identity Center's group
        * 👀-> NO need to set up federation & identity provisioning / EACH application independently👀
    * you enable -- via -- IAM Identity Center's identity store / contains attributes
      * user
        * excluded sign-in credentials
      * group

* ways to keep updated IAM Identity Center's identity store users & groups
  + use IAM Identity Center identity store -- as your -- MAIN identity source 
    + -> ways to manage your users and groups
      + IAM Identity Center console
      + AWS CLI
  + set up provisioning \(synchronization\) of users and groups / from identity sources -- go to -- your IAM Identity Center identity store
    + types of identity sources
      + **Active Directory**
        + see [Connect to a Microsoft AD directory](manage-your-identity-source-ad.md)
      + **External identity provider**
        + see [Connect to an external identity provider](manage-your-identity-source-idp.md)
    + 👀you continue managing your users and groups -- from -- your identity source 👀

## Considerations for sharing identity information in AWS accounts<a name="considerations-app-enablement"></a>

* TODO:
The attributes contained in IAM Identity Center are the basic attributes commonly used across applications\. These attributes include information such as first and last name, phone number, email address, address, and preferred language\. You might want to consider which applications and which accounts can use this personally identifiable information\.

To control access to this information, you have two options\. First, you can choose to enable access in only the AWS Organizations management account or in all AWS Organizations accounts\. Second, you can use service control policies \(SCPs\) to control which applications can access the information in which AWS Organizations accounts\. For example, if you enable access in the AWS Organizations management account only, then applications in member accounts have no access to the information\. However, if you enable access in all accounts, you can use SCPs to disallow access by all applications except those you want to permit\.

## Allow Identity Center enabled applications in AWS accounts<a name="enable-app-enablement"></a>

When you enable IAM Identity Center for the first time, AWS allows use of Identity Center enabled applications automatically in all AWS Organizations accounts\. To constrain applications, you must implement SCPs\.

If you enabled IAM Identity Center prior to November 25, 2019, IAM Identity Center disables the use of Identity Center enabled applications in all AWS Organizations accounts\. To use Identity Center enabled applications, you must enable them in the management account and optionally enable them in member accounts\. If you enable them in the management account only, you can enable them in member accounts in the future\. To enable these applications, use the **Enable access** option in the IAM Identity Center **Settings** page in the Identity Center enabled applications section\.