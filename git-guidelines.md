# Git Guidelines

## Git Commit and Merge Guidelines
- Don’t leave WIPs in the branch history: squash them before merging your code back to `master`. See the “Useful GIT Tools” section for how to add a set of git shortcuts for dealing with WIPs.
    - At the end of the day use `git wip`
    - At the start of each day use `git unwip`
    - It’s reasonable and even encouraged to have a test failing in a WIP
    - It can be helpful to create a manual WIP with a list of todos (though you are welcome to track todos as sub-tasks on the story)
- For large stories that span multiple days, try to create useful real commits (not WIPs) as chunks of functionality get completed.
- Real commits that are kept in history before merging should have all tests passing and be safe to deploy.
- If possible, rebase the main repository branch under your feature changes before merging. This results in a cleaner history that is easier to follow and work with.
- Rebase at least daily, in the morning. This will make your final rebase and merge much easier to deal with.
- If pairing, try not to forget to set the git pair before doing your commits.
- **ALWAYS** run the unit and functional tests *after* rebasing and merging, but *before* pushing to the remote repo.
- Structure your non WIP commit messages in the following style:
    - The first line of the message should be a single sentence summarizing the changes being made. It usually should relate to the story title
    - Leave a blank line below that
    - Then include a detailed explanation of the changes and a bulleted list of specific details that you deem useful for the future
    - Leave another blank line below that
    - Finally the story # in brackets (don’t forget to include the appropriate ticket system integration formatting)

```
Implemented example commit message for coding standards.

Built out the list of requirements and added the to the doc:
* Built a bulleted list of the rules
* Created this example commit message
* Some other details that are useful

[#123456]
```

## Git Commit Template
A template can be configured so that each commit begins with a pre-populated message to help make using the commit message standards easier. In sourcetree, click: Sourcetree -> Preferences -> Commit Template. An example template is as follows:

```
WIP

 *

[]
```

Alternatively, you can create a .stCommitMsg in your home directory, then enable the commit via the global git config by adding the line:

```
[commit]
        template = /Users/<user>/.stCommitMsg
```

## Git Branch Management
There are three primary branch management strategies that should be followed:
1. Individual Feature Development
1. Epic Feature Development
1. Hotfix Bug Development

In all scenarios, completed work should be merged in the repository’s `master` branch. This merging back into the `master` branch should be done only after Engineer has verified that the feature is complete (see [DoD](definition-of-done.md)).

### Individual Feature Development
These stories are not a part of an Epic. 

When beginning work on these stories a feature branch that begins with the story number followed by a meaningful description should be created off the current `master` branch’s top commit. As work is completed please ensure the commits saved in the feature branch represent “safe” states of code that could be independently deployed. If the commit could not be deployed as the top commit of a release, then it should not exist. Make use of the [git rebase](https://onlywei.github.io/explain-git-with-d3/#rebase) feature to squash all WIP commits together. Ideally for small features the entire set of changes are committed in a single git commit.

Upon completion of the feature it should be merged directly back to the `master` branch. Before executing this merge you should rebase the current state of the `master` branch below all of the feature branch’s commits.

### Epic Feature Development
When beginning work on the first story of an epic you must first create a new epic branch off the top of the `master` branch. It should be named using the following convention: “epic/{epic id}-a-meaningful-description”.

All stores within the epic should have their feature branch created off the top commit on the epic branch. Similar to non-epic stories, these feature branches should only have permanent commits that could be safely deployed on their own. When the work for the feature story is complete (see [DoD](definition-of-done.md)), the feature branch should be merged back onto the top of the epic branch. Rebase any epic branch changes before doing this. Proceed to coordinate the delivery of the Epic branch for testing.

Upon successful completion of the epic stories, under the direction of the Product and Engineering Leadership teams, the epic branch should be merged onto the `master` branch in preparation for a release. This process should include rebasing the current `master` branch under the epic branch and resolving any issues. If the rebase is overly difficult to complete a git merge can be used instead.

### Hotfix Bug Development
Hotfix bug development should follow a similar pattern as the Individual Feature Development, except it should always be branched off the top of the “master” branch at the last commit’s git tag. Create a branch with the naming convention of “hotfix/v{major}.{minor}.{patch}”. 

The last commit of the hotfix branch needs to update all version numbers necessary.

For testing, get the hotfix branch itself deployed to one of the testing environments. Upon completion of testing it will also be merged back onto the `master` branch for immediate release. If `master` has moved past the previous commit tag, then the hotfix branch itself should be tagged and used for release purposes (in this case the hotfix branch should still be merged to `master`).

Upon release of a hotfix, the area of the system that was touched by the code should be monitored by the Engineering Team for an appropriate time period depending on the circumstances (usually at least 2-3 days).
