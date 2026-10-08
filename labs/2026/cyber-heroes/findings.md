# Cyber Heroes · Findings

[Case study](README.md) · [Evidence register](evidence/README.md) · [Source export](source/scopelog-export.md)

## Hardcoded credentials in client-side JavaScript

| Field | Record |
| --- | --- |
| Source ID | `F-f66e58ff-511b-42f6-87f2-77640942ef67` |
| Original title | Username & Password |
| Recorded severity | Critical |
| Recorded status | Open |
| Category | Vulnerability |
| Affected component | Login-page JavaScript at `/login.html` |
| Retest | Not recorded |

### Recorded behavior

The finding describes a JavaScript file visible through the browser inspector containing the admin username and password. A simple conditional compared the entered values with the hardcoded pair. The working note describes reading and entering those credentials.

The source's generated narrative reports successful authentication and access to the admin panel. The underlying JavaScript and post-login evidence were not supplied, so this writeup does not independently verify the access level or server-side behavior.

### Recorded reproduction sequence

These steps summarize the source notes for the lab; they were not rerun during this import.

1. Open the HTTP service on the recorded lab target.
2. Navigate to `/login.html`.
3. Open the browser inspector and inspect the login script.
4. Locate the username/password comparison and the readable credential values.
5. Enter the values into the login form; the generated narrative reports successful login.

The exact credentials, script filename, HTTP requests, and code excerpt are absent from the export.

### Impact and limits

Someone able to load the login page could read the embedded credentials. The reported result is access to the admin panel using that pair. There is no supporting record of operating-system access, SSH authentication, credential reuse, data extraction, or other compromise.

Critical is the source assessment's rating. A formal risk score and the full extent of admin capabilities were not recorded.

### Evidence mapping

| Source record | Relevance | Availability |
| --- | --- | --- |
| `E-e91d8d1a-dd78-4a70-87d3-ab223d660dad` | Screenshot described as showing the authentication script | Metadata only; image not supplied |
| `N-a7f6290e-a86d-4269-b1f4-7f9c21aa8bc5` | Tester notes about reading and entering credentials | [Preserved in source](source/scopelog-export.md#research-notes) |

### Proposed remediation

1. Remove the credential pair from browser-delivered code and rotate the exposed password.
2. Authenticate on the server and enforce authorization on protected resources and actions.
3. Store passwords as salted hashes using an appropriate password-hashing scheme rather than reversible encryption.
4. Use server-validated sessions after login and check that unauthenticated requests cannot reach protected functionality.

**Correction to the original advice:** the source suggests encrypting credentials and storing them in a separate file. Keeping the credential or its usable equivalent in browser-accessible material still leaves it exposed. The trust boundary must move to the server.

General implementation references: [OWASP Authentication Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html), [OWASP Password Storage Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html), and [OWASP Session Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html). These are remediation references, not evidence from the lab.

### Proposed retest

After a fix, inspect the delivered page and scripts for exposed credentials, confirm the old credentials no longer work, test access to protected resources without a valid session, and verify valid and invalid login behavior. Record requests, responses, and redacted screenshots before changing this finding's status.

**Current result:** no remediation or retest was supplied; status remains Open.
