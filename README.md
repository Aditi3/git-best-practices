# Git Best Practices

Motivation of this repo is to curate Git best practices at one place and to make more people aware about standards followed by industry. Especially one that involves collaboration with others, it is better to establish conventions to follow lest we shoot ourselves in the foot.

### 1. Make clean, single-purpose commits

A commit should be a wrapper for related changes. For example, fixing two different bugs should produce two separate commits. It is better to keep commits as small and focused as possible for many reasons, some of them includes:

- It makes it easier for other developers in the team to understand the changes, making code reviews more efficient
- If the commit has to be rolled back completely, it's far easier to do so
- Additionally, it helps you parse changes you've made using git log


### 2. Write meaningful commit messages

Insightful and descriptive commit messages that briefly describe what changes are being made as part of a commit make life easier for others as well as your future self. Keep in mind that your team members will need to be able to read this message and understand exactly what you have done.

Some good practice includes:

- Use the imperative, present tense: "change" not "changed" nor "changes" for your commit message 
- Do not end the commit message(subject line) with a period
- Use the body to explain what and why the change was made. This part should be added only when necessary
- Remove unnecessary punctuation marks
- Wrap the subject line aat 50 characters and body at 72 characters

Write your commit message in present tense (up to 50 characters) and always leave the second line blank. This separates your subject line from the body to ensures only the subject line displays. .

The commit message structure as follows/ Format of the commit message:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
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
- `build`: build related changes (eg: npm related/ adding external dependencies

Examples:

### 3. Commit early, commit often

### 4. Pull request norms
