---
"@openid4vc/oauth2": patch
---

Add `allowedClockSkewSeconds` to `Oauth2AuthorizationServer` as the default allowed clock skew for DPoP and client attestation verification in `verifyPushedAuthorizationRequest`, `verifyAuthorizationChallengeRequest`, the `verify*AccessTokenRequest` methods, `verifyDpopJwt` and `verifyClientAttestation`. A per-call `allowedClockSkewSeconds` (DPoP) or `allowedSkewInSeconds` (client attestation) overrides the server default, including `0`.

The `verify*AccessTokenRequest` methods now pass `now` to DPoP proof verification, so the DPoP `iat` checks use the provided time instead of the current time.
