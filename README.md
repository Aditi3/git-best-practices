# Git Best Practices

The purpose of this repository is to gather the best practices for using git in one convenient location and to educate more people about the standards used by the industry. When collaborating with others, it is important to establish conventions to follow.

### 1. Make clean, single-purpose commits

A commit should be a wrapper for related changes. For example, fixing two different bugs should produce two separate commits. It is better to keep commits as small and focused as possible for many reasons, some of them include:

- It makes it easier for other developers in the team to understand the changes, making code reviews more efficient
- If the commit has to be rolled back completely, it's far easier to do so
- It helps you parse changes you've made using the git log


### 2. Write meaningful commit messages

Writing informative and detailed commit messages that give a brief overview of the changes made within a commit is essential for the convenience of others and your own future reference. It's important to consider that your team members will need to comprehend the message and comprehend precisely what changes you have made.

Here are some helpful tips to keep in mind:

- Use the imperative, present tense: "change" not "changed" nor "changes" for your commit message (written in lower case)
- Do not end the commit message(subject line) with a period
- Use the body to explain what and why the change was made. This part should be added only when necessary
- Remove unnecessary punctuation marks
- Wrap the subject line at 50 characters and the body at 72 characters

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
+-------> Type: chore, docs, feat, fix, refac, style, or test
```

"type" must be one of the following:

- `feat`: new feature for the user, not a new feature for build script
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

### 3. Commit early, commit often

I suggest working in smaller portions and frequently committing to your progress instead of striving for perfection. This approach is particularly beneficial when working on a feature branch that may take a while to complete as it ensures that your code remains up-to-date and minimizes potential conflicts.

### 4. Pull request norms

- A PR should be divided into independently mergeable parts also encourages simpler, more decoupled designs. If possible, try to break your PR down into pieces which are independent of each other.
- Each PR review must have at least 1-2 developer approvals. If it’s just a simple docs change or a typo fix, feel free to skip this step.
- Each PR must have a good description. From reading the description, the reviewer should be able to understand what the code is meant to do.

### References
- https://www.conventionalcommits.org
- https://deepsource.io/blog/git-best-practices/
