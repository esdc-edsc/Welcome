# Security Requirements

ESDC IT Security has a few requirements to working on project outside the network (in the Cloud).
If you are working on a project in this space you must be following the requirements listed below.

## Two Factor Authentication (2FA)

For all accounts that are given access to code hosted publicly, their account **must** be enabled with 2FA.
This requires a project to be hosted under a group, where the group can have this setting enforced.
Users with 2FA enabled will require an access token to authenticate from git.  
[https://help.github.com/en/articles/securing-your-account-with-two-factor-authentication-2fa](https://help.github.com/en/articles/securing-your-account-with-two-factor-authentication-2fa)

## Gated Approvals

Merge request or pull request approvals are **required** when modifying code.
When changing the "source of truth" aka *master* branch, there must be some kind of approval by someone who did not change the code.
This is is also just good practice and should be done even inside the network.  
[https://help.github.com/en/articles/enabling-required-status-checks](https://help.github.com/en/articles/enabling-required-status-checks)

**Note:** Under the open GoC license or Crown Copyright you can not accept pull requests from citizens. You can only accept pull requests from GoC employees (from any department).

## Verified Commits

When pushing code to public git repositories, the commit **must** be signed by a GPG key created on the computer you are committing code from and registered with against your user.
[https://help.github.com/en/articles/managing-commit-signature-verification](https://help.github.com/en/articles/managing-commit-signature-verification)
