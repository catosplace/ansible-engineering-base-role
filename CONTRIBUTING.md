# Contributing to the Ansible Engineering Base Role

## Pull Request Process

### Clean verified Git log
Catosplace Engineering like to have a clean verified Git log. To ensure this is maintained please follow the practices set out here.

Using the GitHub UI `Rebase and merge` option within a pull request causes additional commits to be made, and loses the signature verification. The process outlined below ensures a clean and verified Git log.

Do all work in a dedicated branch cut from the `main` branch
```
git checkout main
git checkout -b <BRANCH>
```
When you have completed your work rebase from main, prior to committing to your branch.
```
git rebase main
git commit -m 'COMMIT MESSAGE'
```
When you have pushed and created a pull request checkout main and merge your branch, then push to close the pull request.
```
git checkout main
git merge <BRANCH>
git push
```