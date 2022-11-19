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