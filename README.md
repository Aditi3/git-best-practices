# Git Best Practices

The motivation of this repo is to curate git best practices in one place and make more people aware of standards followed by industry. Especially one that involves collaboration with others, it is better to establish conventions to follow.

### 1. Make clean, single-purpose commits

A commit should be a wrapper for related changes. For example, fixing two different bugs should produce two separate commits. It is better to keep commits as small and focused as possible for many reasons, some of them include:

- It makes it easier for other developers in the team to understand the changes, making code reviews more efficient
- If the commit has to be rolled back completely, it's far easier to do so
- Additionally, it helps you parse changes you've made using git log


### 2. Write meaningful commit messages

Insightful and descriptive commit messages that briefly describe what changes are being made as part of a commit make life easier for others and your future self. Keep in mind that your team members will need to be able to read this message and understand exactly what you have done.

Some good practice includes:

- Use the imperative, present tense: "change" not "changed" nor "changes" for your commit message 
- Do not end the commit message(subject line) with a period
- Use the body to explain what and why the change was made. This part should be added only when necessary
- Remove unnecessary punctuation marks
- Wrap the subject line at 50 characters and body at 72 characters

<p>
<img alt="Light" src="/commit-message.png">
</p> 

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
+-------> Type: chore, docs, feat, fix, refactor, style, or test
```

"type" must be one of the following:

- `feat`: new feature for the user, not a new feature for build script
- `fix`: bug fix for the user, not a fix to a build script
- `docs`: changes to the documentation
- `style`: formatting, missing semi colons, etc; no production code change
- `refactor`: refactoring production code, eg. renaming a variable
- `test`: adding missing tests, refactoring tests; no production code change
- `chore`: regular code maintenance and updating grunt tasks etc; no production code change (eg: change to .gitignore file or .prettierrc file)
- `build`: build related changes, for updating build configuration, development tools or other changes irrelevant to the user (eg: npm related/ adding external dependencies/ podspec related)

#### Examples:

##### Commit message with body and footer

```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Resolves: #123
```

##### Commit message with no body

```
docs: prepare CHANGELOG for version x.x.x
```

### 3. Commit early, commit often

It is better to work in small chunks and keep committing your work, instead of waiting to make it perfect. If you are working on a feature branch that could take some time to finish, it helps you keep your code updated with the latest changes so that you avoid conflicts.

### 4. Pull request norms

- A PR should be divided into independently mergeable parts also encourages simpler, more decoupled designs. If possible, try to break your PR down into pieces which are independent of each other.
- Each PR review must have at least 1-2 developer approvals.
- Each PR must have a good description. From reading the description, the reviewer should be able to understand what the code is meant to do. This has to be true even if there is a Jira ticket or a requirements page.
- If the PR is a bug fix, it must contain a test such that, should the bug fix be reverted, this test would fail.
