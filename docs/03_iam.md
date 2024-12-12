### **IAM Summary Table**

| **IAM Feature**       | **Purpose**                                     | **Key Points**                                                                 |
|------------------------|-------------------------------------------------|-------------------------------------------------------------------------------|
| **Users**             | Represents individuals or applications          | - Credentials: Console (password) or programmatic (Access Key). <br> - Can belong to multiple groups.              |
| **Groups**            | Manage permissions for multiple users           | - Logical collection of users. <br> - Policies are attached to groups, not users.                                   |
| **Policies**          | Define permissions                              | - JSON structure with: <br>  **Effect** (Allow/Deny), **Action**, **Resource**, **Condition** (optional). <br> - Enables fine-grained access control. |
| **Roles**             | Delegate permissions to AWS services            | - Used by services like **EC2** and **Lambda**. <br> - No long-term credentials required; assume roles temporarily. |
| **MFA**               | Adds extra security                             | - Password + physical/virtual device. <br> - Options: Virtual (Google Authenticator), Hardware (YubiKey, Gemalto).  |
| **Password Policy**   | Enforce strong user passwords                   | - Requirements: Minimum length, complexity, expiration, and reuse prevention.                                      |
| **Access Keys**       | Enable programmatic access                      | - Consist of Access Key ID and Secret Access Key. <br> - Never share or hardcode them.                             |
| **Credentials Report**| Audit all users’ credentials                    | - Lists active users and statuses of passwords, keys, and MFA.                                                     |
| **Access Advisor**    | Refine permissions                              | - Shows last service access by users or roles.                                                                     |
| **Least Privilege**   | Security best practice                          | - Grant only the minimum required permissions.                                                                     |

---
