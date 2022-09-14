# SEMANTIC VERSION EXAMPLE

The idea is to create a react project, and define the "gitlab action" to update the change, using semantic versioning

Depending on the commit typo: the version number is going to be modified

| MESSAGE                                                                 | VERSION | RELEASE  |
| :---------------------------------------------------------------------- | :------ | :------- |
| fix(core): fix bug A                                                    | Patch   | Fix      |
| feat(core): new feature B                                               | Minor   | Feature  |
| perf(core): performance improvement on C <br> BREAKING CHANGE: Change D | Major   | Breaking |


# Link
- https://dev.to/amalv/how-to-setup-semantic-release-for-a-react-app-or-a-next-js-app-25c1



## STEPS

1. Create a react `npx create-react-app semantic-release --template typescript --use`
2. Create a github repository `https://github.com/new`
3. Link local repository to Github repository `git remote add origin git@github.com:<username>/<repository-name>.git;git push -u origin master`
4. Github token. A Github token must be created in order for Semantic Release to be able to publish a new release to the Github repository.
5. Save the github token insede  secrets config: `https://github.com/<username>/<repositoryname>/settings/secrets` .Use **GH_TOKEN** as the secret name.
6. Install Semantic Release Git and Changelog plugins `npm install --save-dev @semantic-release/git @semantic-release/changelog`. These plugins are necessary in order to create a Changelog and publish the new release in Github.
7. Add Semantic Release config to package.json
8. Setup Github Actions. Github Actions will be used to create new releases of your app.
You must store workflows in the **.github/workflows** directory in the root of your repository. Once you created the directories, add a **main.yml** file inside with the following config. Use **node-version: 16**
9. Commit and push changes, Use the following commands:
    1. `git add .`
    2. `git commit -m "feat: Add Semantic Release and Github Actions"`
    3. `git push`
10. Congratulations! If you followed these steps, you should now have triggered Github Actions:
11. Also, if you check the release tab in your repository, you'll also see your first published release:
12. And finally, a Changelog file should have been automatically generated and published: