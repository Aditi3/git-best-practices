# Git Best Practices - How to Write Meaningful Commits and Effective Pull Requests

The purpose of this repository is to gather the best practices for using git in one convenient location and to educate more people about the standards used by the industry. When collaborating with others, it is essential to establish conventions to follow.

## Commit Message norms

### 1. Make clean, single-purpose commits

A commit should be a wrapper for related changes. For example, fixing two different bugs should produce two separate commits. It is better to keep commits as small and focused as possible for many reasons, some of them include:

- It makes it easier for other developers in the team and reviewers to understand the changes, making code reviews more efficient
- If the commit has to be rolled back completely, it's far easier to do so
- It helps you parse changes you've made using the git log

### 2. Write meaningful commit messages

I'd like to remind you that writing informative and detailed commit messages that give a brief overview of the changes made within a commit is essential for the convenience of others and your own future reference. It's important to consider that your team members must comprehend the message and precisely what changes you have made.

Here are some helpful tips to keep in mind:

- Use the imperative, present tense: "change" not "changed" nor "changes" for your commit message (written in lower case)
- Do not end the commit message(subject line) with a period
- Use the body to explain what and why the change was made. This part should be added only when necessary
- Remove unnecessary punctuation marks
- Keep it brief, wrap the subject line at 50 characters and the body at 72 characters
- Add an empty line underneath the commit message, and begin writing the body (description)

<p>
<img alt="Light" src="/commit-message.png">
</p> 

### 3. Commit early, commit often

I suggest working in smaller portions and frequently committing to your progress instead of striving for perfection. This approach is particularly beneficial when working on a feature branch that may take a while to complete as it ensures that your code remains up-to-date and minimizes potential conflicts.

#### Format of the commit message:

```
<type>(<optional scope>): <subject>
<BLANK LINE>
<optional body>
<BLANK LINE>
<optional footer(s)>
```
  
```
feat: add foo support
^--^  ^------------^
|     |
|     +-> Summary(commit message subject line) in present tense
|
+-------> Type: chore, docs, feat, fix, refac, style, or test
```

"type" must be one of the following:

- `feat`: new feature for the user, not a new feature for a build script
- `fix`: bug fix for the user, not a fix to a build script
- `docs`: changes to the documentation
- `style`: formatting, missing semi-colons, etc; no production code change
- `refac`: refactoring production code, eg. renaming a variable
- `test`: adding missing tests, refactoring tests; no production code change
- `chore`: regular code maintenance and updating grunt tasks etc; no production code change (eg: change to .gitignore file or .prettierrc file)
- `build`: build-related changes, for updating build configuration, development tools or other changes irrelevant to the user (eg: npm related/ adding external dependencies/ podspec related)
- `perf`: code change that improves performance

#### Examples:

##### Commit message with body and footer

```
fix: prevent racing of requests

Introduce a request id and a reference to the latest request. Dismiss
incoming responses other than from the latest request.

Resolves: #123
```

##### Commit message with body and no footer

```
fix: remove string template from client code

It is incompatible with IE
```

##### Commit message with no body and no footer

```
docs: prepare CHANGELOG for version x.x.x
```

## Pull request norms

- It's recommended to divide PR into independently mergeable parts. This not only promotes simpler designs but also reduces coupling.
- It's best to break down the PR into smaller related commits rather than having a single PR with many changes. Reviewers find it difficult to go through 50+ file changes in one go. 
- At least 1-2 developer approvals are required for a PR review, except for simple changes like typo fixes or documentation updates.
- A well-written description of the PR is crucial for the reviewer to understand the code's purpose.
- Additionally, PR labels can help to give a clearer picture of the PR's status or functionality.

#### Here's an example of a PR with related commit messages -

> feat: add an XYZ support
> 
> test: add unit tests for an XYZ
> 
> docs: add documentation for an XYZ

#### Here's an example of a PR with unrelated commit messages(not recommended) - 

> feat: add an XYZ support
> 
> fix: add fix for ABC feature
> 
> refac: refactor QPR feature code

It seems there is a lot happening and alterations have been made across various sections of the code base. It would be more effective to split up the commit messages into multiple PRs that focus on specific and relevant changes.

## References
- https://www.conventionalcommits.org
- https://deepsource.io/blog/git-best-practices/
