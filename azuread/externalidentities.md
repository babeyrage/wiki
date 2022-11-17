# External Identities

Azure AD External Identities is a set of capabilities that enable organisations to allow access to external users, such as customers or partners. Your customers, partners and other guest users can "bring their own identities" to sign in.

This ability got external users is enabled through Azure AD support of external identity providers like other Azure AD tenants, Facebook, Google or enterprise identity providers. Admins can set up federation with identity providers so your external users can sign in with their existing social or enterprise accounts instead of creating a new account just for the application.

There are two different Azure AD External Identities: **B2B** and **B2C**.
* B2B collaboration allows you to share your apps and resources with external users.
* B2C is an identity management solution for consumer and customer facing apps.

## B2B Collaboration
B2B collaboration allows you to share your organisations application and services with guest users from other organisations, while maintaining control over your own data. B2B collaboration uses an invitation and redemption process. You can also enable self-service sign-up user flows to let external users sign up for apps or resources themselves. Once the external user has redeemed their invitation or completed sign-up, they're represented in the same directory as employees but with a user type of guest. As a guest, they can now access your resources with their credentials.

Guest users can be managed in the same way as employees, added to the same groups etc. With B2B, SSO to all Azure AD-connected apps are supported. 