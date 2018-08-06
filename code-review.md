# Code Review

## Goals of Code Review
- To ensure multiple people understand and can support the code.
- To spread coding expertise, both from the reviewer and from the author.
- To assist in delivering the most reliable, performant, and highest quality product.

## General Process

### 1. Read and Understand the Story
Be sure you have read and understand the story. Ask any questions about the purpose or requirements to either the PM or the Software Engineering Manager.

### 2. Have a Quick Conversation and Demo with the Author
Review the story together. Discuss at a high-level how the author implemented the story. Be sure you have a general understanding of the shape of the code changes and the purpose of the changes. This conversation should also include a demo of the functionality being reviewed.

### 3. Checkout the Feature Branch and Functionally Test the Code
Now that you have an understanding of what the requirements are and how they are met run the code. Be sure that you understand how the feature flows within its context from a user perspective. If you encounter any bugs report them to the author and wait for them to be fixed before proceeding with the code review. Use the debugger and add breakpoints to better understand how the code executes.

### 4. Review the Code via a Pull Request
There should be a Bitbucket pull request that covers all changes to code within the project. Go through all code changes. If possible, review the code in the same order as it would execute. Use the Pull Request to ensure you review all changes to the code, but feel free to read the code in context of the project itself within an editor. Submit recommended changes to the author via comments in the Pull Request and then review them with the author in person.

### 5. Re-review the Code after Changes are Made
Any recommended changes to the code should be re-reviewed before the Pull Request is accepted and merged. Repeat steps 3 and 4 until both the author and the reviewer are confident in the delivery of a quality product.

### 6. Review the DoD with the Author and Merge
Together with the author, do one last review of the Definition of Done. Once the DoD has passed, then accept and merge the Pull Request. The author can then mark the story and finished and can deliver it to the test environment for QC review.

## Guidelines
- **Review code in small chunks.** Try to review at most 400 lines of code at a time. If the Pull Request has more lines of code changed, plan to review the code in multiple phases. Studies have shown that reviewing more code in one sitting reduces the reviewer’s ability to catch defects.
- **Take your time.** Don’t rush your code review. It should take about an hour to review 400-500 lines of code. The goal is to understand the proposed code changes and be able to recommend improvements.
- **Take a break after an hour.** Code review requires a high level of concentration and learning at the same time. Give your brain a break every hour to ensure you can successfully add quality and value to the feature.
- **Be kind.** Review code with the understanding that the author has put forth their best effort and recommend changes in a humble manner. If it helps, reach out and have an in person conversation to review the suggested changes with the author.
- **Be prompt.** To the best of your ability, review code as soon after it is submitted for review as possible. This way the author will not have moved on to a new task and will have fresh context for the story being reviewed.

## Code Review Checklist
- Are the commit messages properly formatted and easy to understand?
- Are any new files well organized within the project?
- Is the code easy to understand and follow?
- Do the automated tests clearly explain the behavior of the new code?
- Are error states handled cleanly and correctly?
- Are all new dependancies necessary and of value?
- Are there any opportunities to refactor shared logic into a service or class?
- Were the styleguide and linting rules followed?
- Do the changes meet the acceptance criteria?
- Does the pull request pass the entire [Definition of Done](definition-of-done.md)?
