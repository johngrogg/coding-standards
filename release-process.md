# Release Process
When preparing a standard release, do the following steps:

- Branch the release branch off of the desired commit, naming it in the “release/v{major}.{minor}.{patch}” convention.
- Bump the version number within the release branch and do any dependancy management activities.
- Verify which stories are in the release, tagging said stories with a “{project}-v{major}.{minor}.{patch}” label/linking to a JIRA version.
- Assist Product Management in creating the Release documentation, including the inclusion of all Pre and Post Deployment Actions in the documentation.
- Deploy the release branch to the Staging environment, in coordination with the QA team. Follow the Release documentation exactly.
- Once all regression testing is completed, at the request of Product Management, merge the release branch into “master”.
    - Create a git tag in the format of “v{major}.{minor}.{patch}” on the merged master commit.
    - Merge the updated master branch back into develop if present (rebase if possible).
    - Clean up fully merged, release feature, epic, and release branches in git.
- Review the final git state with Engineering Leadership.
- The Engineering Team will execute the production deployment using the release’s git tag if continuous deployment is not enabled.

For hotfix releases, the same general process should be followed, except the branch name should be in the format of “hotfix/v{major}.{minor}.{patch}” (as stated in the [Git Branch Management](git-guidelines.md) section.
