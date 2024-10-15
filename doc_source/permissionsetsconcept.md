# Permission sets<a name="permissionsetsconcept"></a>

* == template / 
  * you [create & maintain](permissionsets.md)
  * defines a collection of >=1 [IAM policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)
    * allowed ones
      * [AWS managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#aws-managed-policies)
      * [customer managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#customer-managed-policies)
      * inline policies
      * [AWS managed policies for job functions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_job-functions.html)
  * simplify the assignment of AWS account access / users and groups | your organization
    * ways to assign
      * IAM Identity Center User Portal
      * AWS CLI
    * _Example:_ create a *Database Admin* permission set /
      * includes policies -- for -- administering AWS RDS, DynamoDB, and Aurora services
      * grant access to a list of target AWS accounts | your [AWS Organization](https://aws.amazon.com/organizations/) / your database administrators
  * if you assign a permission set -> IAM Identity Center
    * creates corresponding IAM Identity Center\-controlled IAM roles / EACH account
      * IAM roles -- are managed by -- IAM Identity Center 
    * attaches the policies specified | permission set -- to those -- roles
  * if you modify the permission set -> IAM Identity Center -- updates accordingly -- the corresponding
    * IAM policies
    * IAM roles
  * uses
    * IAM Identity Center –– assigns access to a -- user or group | >=1 AWS accounts -- 👁️ via -- permission sets 👁️

* IAM policies -- can be assigned as a -- [permissions boundary](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_boundaries.html)
  * 👁️== other way around 👁️
  * allowed ones in
    * AWS managed policy
    * customer managed policy

**Topics**
+ [Predefined permissions](permissionsetpredefined.md)
+ [Custom permissions](permissionsetcustom.md)