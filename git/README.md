# Infonomic Git Usage Guide

[Git](https://git-scm.com/) usage at Infonomic mainly follows other 'best practice' guides and documentation - including a variation of trunk-based git branching strategy described 
<a href="https://www.atlassian.com/continuous-delivery/continuous-integration/trunk-based-development" target="_blank" rel="noopener nofollow">here</a>.

Here's an excellent Git presentation from a 'friend of Infonomic' - Alexander Groß - <a href="https://agross.github.io/git-reveal/#/" target="_blank" rel="noopener nofollow">Git Reveal</a>

And a very good article that describes several Git branch workflow strategies - <a href="https://www.endoflineblog.com/oneflow-a-git-branching-model-and-workflow" target="_blank" rel="noopener nofollow">OneFlow – a Git branching model and workflow</a>

## Branch Workflow

Infonomic's current branch strategy is as follows:

<img style="display:block;margin:0 auto; max-width: 400px;" src="https://github.com/infonomic/guides/blob/main/git/Git-Branch-Strategy_01.png" alt="Git branch strategy" />


  - **main**: is the currently deployed production release and should not be touched by anyone other than the release manager.
  - **staging**: is the branch used for staging deploys and QA of a release candidate and should not be touched by anyone other than the release manager.
  - **develop**: contains non-blocking release candidates for testing, QA, as well as any changes or fixes that are safe to share across all feature branches. `develop` will be merged into `staging` for a staged deploy, and so should never contain code that will prevent a staging deploy.
  - **feat/&lt;feature-name&gt;**: is a feature branch. Feature branches are where code is actively developed and are named `feat/topic`, `feat/longer-name-topic`, `feat/some-other-feature`. Feature branches when 'ready' are merged into `develop` for testing, QA, and in preparation for a staged deploy. Feature branches may also be deployed for preview-release testing to a test or staging environment.
  - **hotfix**: is used to create named hotfix branches that will be merged directly into `main` in order to fix a production bug - for example: `hotfix/foo-exception`, `hotfix/render-regression` etc.

## Commit messages

Infonomic currently follows the [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) naming strategy. Below is a cheat sheet for commit prefixes.

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

- `feat`: new feature for the user, not a new feature for build script
- `fix`: bug fix for the user, not a fix to a build script
- `docs`: changes to the documentation
- `style`: formatting, missing semi colons, etc; no production code change
- `refactor`: refactoring production code, eg. renaming a variable
- `test`: adding missing tests, refactoring tests; no production code change
- `chore`: updating grunt tasks etc; no production code change

More Examples: 

- `chore`: add Oyster build script
- `docs`: explain hat wobble
- `feat`: add beta sequence
- `fix`: remove broken confirmation message
- `refactor`: share logic between 4d3d3d3 and flarhgunnstow
- `style`: convert tabs to spaces
- `test`: ensure Tayne retains clothing

References:

- <a href="https://www.conventionalcommits.org/" target="_blank" rel="noopener nofollow">https://www.conventionalcommits.org/</a>
- <a href="https://dev.to/i5han3/git-commit-message-convention-that-you-can-follow-1709" target="_blank" rel="noopener nofollow">https://dev.to/i5han3/git-commit-message-convention-that-you-can-follow-1709</a>
- <a href="https://seesparkbox.com/foundry/semantic_commit_messages" target="_blank" rel="noopener nofollow">https://seesparkbox.com/foundry/-semantic_commit_messages</a>
- <a href="http://karma-runner.github.io/1.0/dev/git-commit-msg.html" target="_blank" rel="noopener nofollow">http://karma-runner.github.io/1.0dev/git-commit-msg.html</a>
