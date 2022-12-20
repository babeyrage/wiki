# Azure Identity Types

Azure AD manages different types of identities: users, service principals, managed indentities and devices. 

## User

A user identity is a representation of something that's managed by Azure AD. Employees and guests are represented as users in Azure AD. 

* Several users with the same access needs can be grouped to give access permissions to all members of the group, instead of having to assign access rights individually. 

Azure AD business-to-business (B2B) collaboration, a feature within External Identities, includes the capability to add guest users. With B2B collaboration, an organisation can securely share applications and services with guest users from another organisation. 

## Service Principal
A service principal is an identity for an application. For an application to delegate its identity and access functions to Azure AD, the application must first be registered with Azure AD to enable its integration. Once registered, a service principal is created in each Azure AD tenant where the application is used. The service principal enables core features such as authenication and authorisation of the application to resources that are secured by the Azure AD tenant.

For the service principals to be able to access resources secured by the Azure AD tenant, application developers must manage and protect the credentials. 

## Managed Identity
Managed identities are a type of service principal that are autoamtically managed in Azure AD and eliminate the need for developers to manage credentials. Managed identities provide an identity for applications to use when connecting to Azure resources that support Azure AD authentication and can be used without any extra cost.

There are two types of managed indentities: **system-assigned** and **user-assigned**. 

**System-assigned**: Some Azure services allows you to enable a managed identity directly on a service instance. When you enable a system-assigned managed identity, an identity is created in Azure AD thats tied to the lifecycle of that service instance. When the resource is deleted, Azure automatically deletes the identity, and only that Azure resource can use this identity to request tokens from Azure AD. 

**User-assigned**: Managed identities can also be created as a standable Azure resource. Once a user-assigned managed identity is created, you can assign it to one or more instances of an Azure service. With user-assigned maanged identities, the identity is managed separately from the resources that use it.

## Device
A device is a piece of hardware, such as mobile devices, laptops, servers etc. A device identity gives you adminstrators information they can use when making access or configuration decisions. Device identities can be set up in different ways in Azure AD.

* **Azure AD registered devices**: The goal of Azure AD registered devices to provide users with support for BYOD or mobile device scenarios. In these scenarios, a user can access your organisation's resources using a personal device. Azure AD registered devices register to Azure AD without requiring an organisational account to sign in to the device. Supported operating systems for Azure AD registered devices include Windows 10 and above, iOS, Android and macOS.
* **Azure AD Joined**: An Azure AD joined device is a device joined to Azure AD through an organisational account, which is then used to sign in to the device. Azure AD joined devices are generally owned by the organisation. Supported operating systems for Azure AD joined devices include Windows 10 or greater (except Home Edition) and Windows Server 2019 Virtual Machines running in Azure.
* **Hybrid Azure AD Joined Devices**: Organisations with existing on-premises Active Directory implementations can benefit from the functionality provided by Azure AD by implementing hybrid Azure AD joined devices. These devices are joined to your on-premises AD and Azure AD requiring organisational account to sign in to the device.

Registering and joining devices to Azure AD gives users SSO to cloud-based resources. Additionally, devices that are Azure AD joined benefit from the SSO experience to resources and applications that rely on on-premises AD.
