# Azure Active Directory

Microsoft Azure Directory (Azure AD) is Microsoft's cloud-based identity and access management service. Organisations use Azure AD to enable their employees, guests, and others to sign in and access the resources they need.

Azure AD:
* Simplifies the way organisations manage authorisation and access by providing a single identity system (SSO) for their cloud and on-premises applications
* Can be synchronised with your existing on-premises Active Directory (AD), synchronised with other directory services or used as a standable service. 
* Allows organisations to securely enable the use of personal devices
* Enable collaboration with business partners and customers
* Control access to corporate apps and resources, based on business requirements 
* Set up to require multi-factor authentication when accessing important organisational resources 
* Can be used to automate user provisioning between an existing Windows Server AD and cloud apps, including Microsoft 365 
* Provides powerful tools to automatically help protect user identities, credentials and to meet an organisation's access goverance requirements

Developers use Azure AD as a standards-based approach for adding SSO to their apps, so that users can sign in with their pre-existing credentials. Azure AD also provides APIs that allow developers to build personalised app experiences using existing organisational data. 

Subscribers to Azure services, Microsoft 365 or Dynamics 365 automatically have access to Azure AD. Users of these services can take advantage of included Azure AD services and can also enhance their Azure AD implementation by upgrading to Azure Premium licenses. 

# Azure AD Editions
Azure AD is available in four editions: Free, Office 365 Apps, Premium P1 and Premium P2. 

**Azure Active Directory Free**: 
* Administering of users and create groups
* Synchronise with on-premises AD
* Create basic reports
* Configure self-service password change for cloud users
* Enable SSO across Azure, Microsoft 365 and other SaaS apps
* Included in subscriptions to:
	* Office 365
	* Azure
	* Dynamics 365
	* Intune
	* Power Platform

**Office 365 Apps**: 
* Everything included in free version
* Self-service password reset for cloud users
* Device write-back (which offers two-way synchronisation between on-premises directories and Azure AD)
* Included in subscriptions to:
	* Office 365 E1, E3, E5, F1 & F3

**Azure Active Directory Premium P1**: 
* Everything included in free and Office 365 Apps
* Advanced administration:
	* Dynamic groups
	* Self-service group management
	* Microsoft Identity Manager (an on-premises identity and access management suite)
	* Cloud write-back capabilities - which allow self-service password reset for on-premise users

**Azure Active Directory Premium P2**: 
* Everything included in Premium P1
* Azure Active Directory Identity Protection - provides risk-based Conditional Access to apps and critical data
* Privileged Identity Management - discover, restrict and monitor administrators and access to resources and provide just-in-time access when needed

# Azure Identity Types
Azure AD manages different types of identities: users, service principals, managed indentities and devices. 

### User
A user identity is a representation of something that's managed by Azure AD. Employees and guests are represented as users in Azure AD. 

* Several users with the same access needs can be grouped to give access permissions to all members of the group, instead of having to assign access rights individually. 

Azure AD business-to-business (B2B) collaboration, a feature within External Identities, includes the capability to add guest users. With B2B collaboration, an organisation can securely share applications and services with guest users from another organisation. 

### Service Principal
A service principal is an identity for an application. For an application to delegate its identity and access functions to Azure AD, the application must first be registered with Azure AD to enable its integration. Once registered, a service principal is created in each Azure AD tenant where the application is used. The service principal enables core features such as authenication and authorisation of the application to resources that are secured by the Azure AD tenant.

For the service principals to be able to access resources secured by the Azure AD tenant, application developers must manage and protect the credentials. 

### Managed Identity
Managed identities are a type of service principal that are autoamtically managed in Azure AD and eliminate the need for developers to manage credentials. Managed identities provide an identity for applications to use when connecting to Azure resources that support Azure AD authentication and can be used without any extra cost.

There are two types of managed indentities: **system-assigned** and **user-assigned**. 

**System-assigned**: Some Azure services allows you to enable a managed identity directly on a service instance. When you enable a system-assigned managed identity, an identity is created in Azure AD thats tied to the lifecycle of that service instance. When the resource is deleted, Azure automatically deletes the identity, and only that Azure resource can use this identity to request tokens from Azure AD. 

**User-assigned**: Managed identities can also be created as a standable Azure resource. Once a user-assigned managed identity is created, you can assign it to one or more instances of an Azure service. With user-assigned maanged identities, the identity is managed separately from the resources that use it.

### Device
A device is a piece of hardware, such as mobile devices, laptops, servers etc. A device identity gives you adminstrators information they can use when making access or configuration decisions. Device identities can be set up in different ways in Azure AD.

* **Azure AD registered devices**: The goal of Azure AD registered devices to provide users with support for BYOD or mobile device scenarios. In these scenarios, a user can access your organisation's resources using a personal device. Azure AD registered devices register to Azure AD without requiring an organisational account to sign in to the device. Supported operating systems for Azure AD registered devices include Windows 10 and above, iOS, Android and macOS.
* **Azure AD Joined**: An Azure AD joined device is a device joined to Azure AD through an organisational account, which is then used to sign in to the device. Azure AD joined devices are generally owned by the organisation. Supported operating systems for Azure AD joined devices include Windows 10 or greater (except Home Edition) and Windows Server 2019 Virtual Machines running in Azure.
* **Hybrid Azure AD Joined Devices**: Organisations with existing on-premises Active Directory implementations can benefit from the functionality provided by Azure AD by implementing hybrid Azure AD joined devices. These devices are joined to your on-premises AD and Azure AD requiring organisational account to sign in to the device.

Registering and joining devices to Azure AD gives users SSO to cloud-based resources. Additionally, devices that are Azure AD joined benefit from the SSO experience to resources and applications that rely on on-premises AD.

# External Identities
Azure AD External Identities is a set of capabilities that enable organisations to allow access to external users, such as customers or partners. Your customers, partners and other guest users can "bring their own identities" to sign in.

This ability got external users is enabled through Azure AD support of external identity providers like other Azure AD tenants, Facebook, Google or enterprise identity providers. Admins can set up federation with identity providers so your external users can sign in with their existing social or enterprise accounts instead of creating a new account just for the application.

Azure AD External Identities is a feature of Premium P1 and P2 editions and pricing is based on monthly active users.

There are two different Azure AD External Identities: **B2B** and **B2C**.
* B2B collaboration allows you to share your apps and resources with external users.
* B2C is an identity management solution for consumer and customer facing apps.

### B2B Collaboration
B2B collaboration allows you to share your organisations application and services with guest users from other organisations, while maintaining control over your own data. B2B collaboration uses an invitation and redemption process. You can also enable self-service sign-up user flows to let external users sign up for apps or resources themselves. Once the external user has redeemed their invitation or completed sign-up, they're represented in the same directory as employees but with a user type of guest. As a guest, they can now access your resources with their credentials.

Guest users can be managed in the same way as employees, added to the same groups etc. With B2B, SSO to all Azure AD-connected apps are supported. 

### B2C Access Management
Azure AD B2C is a customer identity access management (CIAM) solution. Azure AD B2C allows external users to sign in with their preferred social, enterpise or local account identities to get SSO to your applications. It takes care of the scaling and safety of the authenication platform, monitoring and automatically handling threats like DDOS, password spray or brute force attacks. 

With Azure AD B2C, external users are managed in the Azure AD B2C directory, separately from the organisation's employee and partner directory. SSO to customer owned apps within the Azure AD B2C tenant is also supported, and can be customised to suit the brand and blend in with the organisation's web and mobile applications.

# Conditional Access in Azure AD
Conditional Access is a feature of Azure AD that provides an extra layer of security before allowing authenticated users to access data or other assets, and is implemented through policies that are created and managed in Azure AD. A Conditional Access policy analyses signals including user, location, device, application and risk to automate decisions for authorising access to resources (apps and data).

![[Pasted image 20221118000211.png]]

A Conditional Access policy might state that *if* a user belongs to a certain group, then they're required to provide MFA to sign in to an application.

## Conditional Access Signals
Some of the common signals that Conditional Access can take in to account when making a policy decision may include:

* **User or group membership** - Policies can be targeted to all users, specific groups of users, directory roles or external guest users, giving administrators fine-grained control over access.
* **Named location information** - Named location information can be created using IP address ranges, and used when making policy decisions. Also, adminstrators can opt to block or allow traffic from an entire country/region's IP range.
* **Device** - Users with devices of specific platforms or marked with a specific state can be used.
* **Application** - Users attempting to access specific applications can trigger different Conditional Access policies.
* **Real-time sign-in risk detection** - Signals integration with Azure AD Identity Protection allows Conditional Access policies to identify risky sign-in behavior - the probability that a given sign-in, or authentication request, isn't authorised by the identity owner. Policies can then force users to perform password changes or MFA to reduce their risk level or be blocked from access until an administrator takes manual action.
* **Cloud apps or actions** - Cloud apps or actions can include or exclude cloud applications or user actions that will be subject to the policy.
* **User risk** - For customers with access to Identity Protection, user risk can be evaluated as part of a Conditional Access policy. User risk represents the probability that a given identity or account is compromised. User risk can be configured for high, medium or low probability. 

When creating a conditional access policy, admins can determine which signals to use through assignments. The assignments portion of the policy controls the who, what and where of the Conditional Access policy. All assignments are logically ANDed. If there is more than one assignment configured, all assignments must be satisfied to trigger a policy.

## Access Controls
When the Conditional Access policy has been applied, an informed decision is reached on whether to grant access, block access, or require extra verification. 

Common decisions are:
* Block access
* Grant access
* Require one or more conditions to be met before granting access:
	* Require MFA
	* Require device to be marked as compliant
	* Require hybrid Azure AD joined device
	* Require approved client app
	* Require app protection policy
	* Require password change
* Control user access based on session controls to enable limited experiences within specific cloud applications. 

Conditional Access policies can be targeted to members of specific groups or guests. **Conditional Access is a feature of paid Azure AD editions**.

# Azure AD Roles & Role-based Access Control
Azure AD roles control permissions to manage resources. Managing access using roles is role-based access control (RBAC). 

## Built-in Roles

Most common built-in roles are:

* *Global administrator* 
	* Access to all administrative features
	* Person who signs up for Azure AD tenant is automatically a global admin
* *User administrator* 
	* Can create and manage all aspects of users and groups
	* Manage support tickets 
	* Monitor service health
* *Billing administrator* 
	* Makes purchases and manage subscription
	* Manage support tickets
	* Monitor service health

## Custom Roles

A custom role definition is a collection of permissions that you choose from a preset list. The list of permissions to choose from are the same permissions used by the built-in roles, the difference is you get to choose which permissions to include in a custom role. **Custom roles require an Azure AD Premium P1 or p2 license**.

Granting permission is a two-step process.

1. Create a custom role definition - collection of permissions added from a preset list
2. Assign role to user or groups through a role assignment

A role assignment grants the user the permissions in a role definition, at a specified scope, which defines the set of Azure AD resources the role member has access to.

A custom role can be assigned at 2 different scopes:

1. Organisation-wide scope - role permissions over all resources
2. Object scope - specific applications

## Categories of Azure AD Roles

Azure AD built-in roles differ in where they can be used and broken up into three broad categories.

* *Azure AD-specific roles*: Grant permissions to manage within Azure AD only
* *Service-specific roles*: Grant permissions to maange features within a specific service
* *Cross-service roles*: Some roles within Azure AD span services
	* Example: Security Administrator grants access across multiple security services with Microsoft 365

![[Pasted image 20221118160034.png]]

## Difference Between Azure AD RBAC & Azure RBAC

* Azure AD RBAC - controls access to Azure AD resources such as users, groups and applications
* Azure RBAC - controls access to Azure resources such as virtual machines or storage using Azure Resource Management

There are different data stores where role definitions and role assignments are stored, and different policy decison points where access checks happen.
