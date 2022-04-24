# Infonomic Git Usage Guide

[Git](https://git-scm.com/) usage at Infonomic mainly follows other 'best practice' guides and documentation - including [Git book](https://git-scm.com/book/en/v2), [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) and a variation of trunk-based git branching strategy described [here](https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development) and [here](https://www.toptal.com/software/trunk-based-development-git-flow) 

Here's an excellent Git presentation from a 'friend of Infonomic' - Alexander Groß - https://agross.github.io/git-reveal/#/ 

And a very good article that describes several Git branch workflow strategies ....

[OneFlow – a Git branching model and workflow](https://www.endoflineblog.com/oneflow-a-git-branching-model-and-workflow)

## Branch Workflow

Infonomic currently follows the following branch strategy:

  - **main**: is the currently deployed production release, and should NOT be touched by anyone other than the release manager.
  - **staging**: is the branch used for stated deploys and QA of a release candidate and should NOT be touched by anyone other than the release manager.
  - **develop**: is the branch containing non-blocking release candidates for QA, testing, and minor changes or fixes. Develop will be merged into `staging` for a staged deploy, and so should never contain code that will prevent a staging deploy.
  - **feat/feature-name**: Topic or feature branches are where code is actively developed and are named `feat/topic`, `feat/longer-name-topic`, `feat/some-other-feature`. Topic branches when 'ready' are merged into develop for testing, QA, and in preparation for a staged deploy. Topic branches may also be deployed for preview-release testing to a test or staging environment.
  - **hotfix**: is used to create named hotfix branches that will be merged directly into main - for example: `hotfix/foo-exception`, `hotfix/render-regression` etc.

## Commit messages

Infonomic currently follows the [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) naming strategy. Below is a cheat-sheet for commit prefixes.

Format: `<type>(<scope>): <subject>`

`<scope>` is optional

## Example

```
feat: add hat wobble
^--^  ^------------^
|     |
|     +-> Summary in present tense.
|
+-------> Type: chore, docs, feat, fix, refactor, style, or test.
```

Examples:

- `feat`: (new feature for the user, not a new feature for build script)
- `fix`: (bug fix for the user, not a fix to a build script)
- `docs`: (changes to the documentation)
- `style`: (formatting, missing semi colons, etc; no production code change)
- `refactor`: (refactoring production code, eg. renaming a variable)
- `test`: (adding missing tests, refactoring tests; no production code change)
- `chore`: (updating grunt tasks etc; no production code change)

More Examples: 

- `chore`: add Oyster build script
- `docs`: explain hat wobble
- `feat`: add beta sequence
- `fix`: remove broken confirmation message
- `refactor`: share logic between 4d3d3d3 and flarhgunnstow
- `style`: convert tabs to spaces
- `test`: ensure Tayne retains clothing

References:

- https://www.conventionalcommits.org/
- https://dev.to/i5han3/git-commit-message-convention-that-you-can-follow-1709
- https://seesparkbox.com/foundry/semantic_commit_messages
- http://karma-runner.github.io/1.0/dev/git-commit-msg.html