# pull-request-based-release-template

Create a release using pull requests.

It was created as a sample repository for the following.

- [slime-hatena/lerna-changelog-action](https://github.com/slime-hatena/lerna-changelog-action)
- [slime-hatena/semantic-versioning-calculator-action](https://github.com/slime-hatena/semantic-versioning-calculator-action)

## About the Repository

Use GitHub Actions to do these automatically.

- Add tags during initialization.
- Maintain proper tagging.
- Create a Pull Request for the branch to be used for the release.
- Automatically create a release with release notes.

This is a git-flow with the release branch removed.

## How to use

1. Create a future branch, a fix branch, etc. from the main branch.  
The changelog will be generated using the title of the pull request. Make only one change per branch.
2. When the work is complete, create a pull request to the develop branch.
3. When the Pull Request is merged, the `main...develop` Pull Request will be updated.
4. When you are ready to release, approve the Pull Request for the release. Check the version and release notes for the next release to make sure they are correct.
5. Make sure that you have created the release correctly and that you have created a develop branch for the next time.

\* If you find a bug that needs to be fixed urgently, create a hotfix branch, and treat it as you would a develop branch. (Create a new branch. When it's done, merge it into hotfix, set the Release tag, and merge it into main branch.)

## Todo

Doing these will make it a better repository.

- [ ] Modify README.md to match the contents of the repository.
- [ ] Create a LICENSE. Make it easy to use the code by clearly stating the license for users.
- [ ] If your build requires additional steps, you may want to include them in `.github/workflows/create_release.yml`.
- [ ] To customize the label, edit `.github/labels.json`. To apply the changes, run the Label maintenance Action. manually.
- [ ] Create a `dependabot.yml` if necessary. You may want to add the following settings: labels: - 'Type: Maintenance', target-branch: "develop".
- [ ] The following settings can be added to ensure safe operation.
  - [ ] Setting -> Option -> Automatically delete head branches. / true.  
    By not leaving any branches after the work is done, you can do a clean job.
  - [ ] Setting -> Branch protection rules. / Setup into main.  
    - [ ]Require status checks to pass before merging. & Require branches to be up to date before merging.
    - [ ] Require conversation resolution before merging.
    - [ ] Include administrators.
