---
appliesTo:
- type: capability
  id: deactivate-user
- type: capability
  id: delete-user
- type: capability
  id: set-user-role
references:
- kind: code
  role: implementation
  target: actions/admin/users/deactivate-user.ts#deactivateUser
- kind: code
  role: implementation
  target: actions/admin/users/delete-user.ts#deleteUser
- kind: code
  role: implementation
  target: actions/admin/users/set-role.ts#setUserRole
---

# An admin never deactivates, deletes or demotes themselves

Deactivating oneself, deleting oneself and setting one's own role to anything but admin are refused, so an instance cannot lose its last admin by accident.
