# Organization Service Keys

Organization service keys let an integration obtain API tokens without a person generating a new token each time. Keys belong to a Wildbook organization and use its dedicated service account. They do not use the personal access rights of the administrator who created them.

This feature is available in Wildbook 11.0. For a one-time analysis or interactive task, start with a [personal API token](api-access.md).

## Who Can Manage Keys?

- **Site administrators** can manage keys for any organization.
- Users with the **orgAdmin** role can manage keys for organizations they belong to directly.
- The **orgSuper** role alone does not grant key-management access. Membership in a parent organization alone does not grant access to a child organization's keys.

Managing keys requires confirming your Wildbook password. A browser session, personal API token, or service key alone cannot manage keys.

## Create a Service Key

1. Sign in and select **API Access** from your account menu.
2. Select **Manage service keys**, enter your password, and select **Confirm**.
3. In **Organization service keys**, select the intended **Organization**.
4. Under **Create service key**, enter a **Label** that identifies the integration, such as `Monthly catalog analysis`.
5. Select the required **Scopes** from the table below.
6. Set **Valid for (days, 1-365)**. The default is 90 days.
7. Select **Create service key** and confirm your password.
8. Copy the key into your integration's secret store before selecting **Done** or closing the panel. The complete key is shown only once.

Each organization can have at most **two active keys**. An active key has not expired or been revoked. Use the second slot to replace a key without interrupting the integration.

| Scope | Allows the integration to request |
| --- | --- |
| `data:read` | Tokens for the general read API, limited to data the service account can access |
| `submissions:read` | Tokens to read that service account's submission status and results |
| `submissions:write` | Tokens to create, upload, validate, and commit submissions, and read their status and results |

Select only the scopes the integration needs. A key can allow more than one scope, but each token is issued for one purpose. A key with `submissions:write` can also request a `submissions:read` token. Neither submission scope grants access to the general read API.

Creating the first key provisions the organization's service account. That account cannot sign in through the normal password login flow. Access checks use the service account's permissions, not the key creator's permissions.

For submission writes, a **site administrator must separately grant api-submission to the organization's service account**, and the submissions pilot must be enabled. Selecting `submissions:write` when creating a key does not enroll the account or enable the pilot. See {ref}`Data Import Access <api-access-data-import>`.

## Exchange a Key for a Token

A service key begins with `wbsvc_`. Send it only to the token endpoint on the Wildbook that issued it. The following HTTP example uses a placeholder, not a real credential:

```http
POST /api/v3/auth/token?scope=data:read HTTP/1.1
Authorization: Bearer wbsvc_<key-id>.<secret>
```

Omitting `scope` requests the same general read access as `scope=data:read`. Use `scope=submissions:read` or `scope=submissions:write` for the submission workflow.

A successful response includes:

- `token`: the short-lived bearer token to use for API requests.
- `tokenType`: `Bearer`.
- `expiresInSeconds`: how long that token remains valid.
- `keyExpiresAt`: the service key's expiration as milliseconds since the Unix epoch.

Send the returned **token**, rather than the service key, to the API routes documented by your Wildbook:

```text
Authorization: Bearer <returned-token>
```

Reuse the token until it is close to expiry, then exchange the service key again. Do not exchange the key before every API request. Service-key tokens last **at most 15 minutes**, may be shorter depending on server configuration, and cannot outlive the key. Use the response's `expiresInSeconds` to schedule renewal.

Store the service key in the integration's secret store. Keep it out of chat, source files, URLs, and logs. For request examples and data access details, fetch `/api/v3/agent-skill/api-reference` from your Wildbook; for submissions, fetch `/api/v3/agent-skill/submit-sightings`.

## Review, Replace, or Revoke Keys

The key list shows each key's label, scopes, expiration, creator, last use, and status. **Last used** records a successful exchange for a token; it is not a record of every API request. **Never** means no successful exchange has been recorded.

To replace a key before it expires:

1. Create a replacement with the scopes the integration needs.
2. Update the integration's secret store.
3. Confirm that it can exchange the replacement and perform its intended API requests.
4. Select **Revoke** for the old key, confirm the action, and enter your password.

If both active-key slots are occupied, identify which key can be retired before creating another. If you lose a key's secret, revoke it and create a replacement; the existing secret cannot be displayed again.

To stop one integration's key from issuing tokens, select **Revoke** beside it. **Revoke all** revokes every key for the selected organization and can interrupt every integration using those keys.

Revocation prevents further token exchanges immediately. Tokens already issued can continue working until they expire, for at most 15 minutes. Revocation is permanent; create a new key if access is needed again.

## Troubleshooting

| Problem | What to check |
| --- | --- |
| **Manage service keys** is missing | Confirm that your account has the **admin** or **orgAdmin** role and that your Wildbook supports this feature. |
| **No organizations are available for service keys** | An organization administrator must be a direct member of the organization. Ask a site administrator to check membership and roles. |
| The organization already has two active keys | Revoke a key that is no longer needed before creating another. |
| The service account needs attention | Ask a site administrator to restore its eligibility. It must belong directly to its own organization only and must not have **admin**, **orgAdmin**, or **orgSuper** roles. |
| Token exchange returns `401` | Check whether the key is invalid, expired, revoked, or unavailable. A revoked or expired key must be replaced. |
| Token exchange returns `403` | Check that the key allows the requested scope. Submission writes also require service-account enrollment and enabled submission admission. |
| Token exchange returns `503` | Ask the operator to check token issuance and service-account configuration. |
| The token cannot see expected data | Check the service account's data access. The key does not inherit the administrator's personal access. |

For site operators, service keys and submission enrollment use `context0` in Wildbook 11.0. Keep the service account attached to its owning organization; changing its membership or granting administrative roles can make its keys unusable.
