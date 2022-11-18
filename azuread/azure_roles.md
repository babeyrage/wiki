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
