# Access Control Lists

An [access control list](https://learn.microsoft.com/en-us/windows/win32/secauthz/access-control-lists?redirectedfrom=MSDN) (ACL) is a list of access control entries (ACE). Each ACE in an ACL identifies a trustee and specifies the access rights allowed, denied or audited for tha trustee. The security descriptor for a securable object can contain two types of ACLs: a DACL and a SACL.

A discretionary access control list (DACL) identifies the trustees that are allowed or denied access to a securable object. When a process tries to access a securable object, the system checks the ACEs in the objects DACL to determine whether to grant access to it. If the object does not have a DACL, the system grants full access to everyone. If the object's DACL has no ACEs, the system denies all attempts to acess the object because the DACL does not allow any access rights. The system checks the ACEs in sequence until it finds one or more ACEs that allow all the requested access rights, or until any of the requested access rights are denied.

A system access control list (SACL) enables administrators to log attempts to access a secured object. Each ACE specifies the types of attempts by a specified trustee that cause the system to generate a record in the security even log. An ACE in a SACL can generate audit record when an access attempt fails, when it succeeds or both.

**Do not try to work directly with the contents of an ACL. To ensure that ACLs are semantically correct, use the appropriate functions to create and minipulate ACLs.** 