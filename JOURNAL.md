# PathReview — Module 3 Journal

## Week 7 — Issue selection

**Issue link:** https://github.com/jamjamgobambam/pathreview/issues/90

**Issue title:** Add integration tests for authentication edge cases

**Tier:** [ ] Tier 1  [x] Tier 2  [ ] Tier 3

**Problem summary:**
The auth middleware currently only has coverage for the happy path — a single
request carrying a valid JWT. That leaves every failure mode untested, so a
regression in how the API rejects bad credentials could ship unnoticed. This
issue asks for integration tests covering the rejection paths: an expired
token, a malformed/garbage token, a completely missing `Authorization` header,
and a token that is well-formed but signed with the wrong secret. A successful
fix adds these cases to `tests/integration/test_auth_middleware.py`, each
asserting the middleware returns the correct 401 response, so the auth layer's
guarantees are locked in against future changes.

**Branch name:** test/90-auth-middleware-edge-cases

**Setup confirmation:** [ ] App runs locally at localhost:5173

**Cohort ledger:** [ ] Issue added to cohort ledger
