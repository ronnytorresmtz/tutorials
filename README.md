# TUTORIALS
Some links to good tutorials or articles for Vue and Laravel


## Laravel

 1. <b> Starting with Laravel Echo and PusherJS </b>  [more](https://petericebear.github.io/starting-laravel-echo-20170303/)
- <em> Laravel Echo is a JavaScript library that makes it painless to subscribe to channels and listen for events broadcast by Laravel. [more](https://laravel.com/docs/5.8/broadcasting) </em>
- <em> Pusher Channels provides realtime communication between servers, apps and devices. Pusher Channels is used for notifications, chat, gaming, web-page updates, IoT, and many other systems requiring realtime communication. [more](https://pusher.com/docs) </em>


## Nova Laravel

1. <b> Enable VueTools </b>
```
cd ./vendor/laravel/nova
mv webpack.mix.js.dist webpack.mix.js
npm i
npm run dev
rm -rf node_modules
cd -
php artisan nova:publish
```

# Git Flow

1. <b> Successful Git Branching Model</b> [more](https://nvie.com/posts/a-successful-git-branching-model/) [PDF](https://github.com/ronnytorresmtz/tutorials/blob/master/Git-branching-model.pdf)
- master branch 
- develp branch
- Feature branches
- Release branches
- Hotfix branches
2. <b> Prevet Commits on Master Branch </b> [more](https://stackoverflow.com/questions/40462111/git-prevent-commits-in-master-branch)
3. <b> Git Guide from Attlasian </b> [more](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)
4. <b> Git Cheat Sheet </b> [more](https://github.com/ronnytorresmtz/tutorials/blob/master/atlassian-git-cheatsheet.pdf)
5. <b> Git Basics Instructions </b>

## Master Branch
### Create Repository
- Create a new repository on the command line 
```
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/ronnytorresmtz/test.git
git push -u origin master
```
- Push an existing repository from the command line
```
git remote add origin https://github.com/ronnytorresmtz/test.git
git push -u origin master
```
- List all branches (local and remotes)
```
git branch -a
```
## Develop Branch
### Create Develop Branch
- Create a new branch, named develop and switch to develop branch
```
git checkout -b develop
```
- Change to master branch
```
git checkout master
```
### Commit Changes and Push to Branch
- Add all file to stage
```
git add .
```
- Commit changes for the file in stage with a commit description
```
git commit -m "first commit"
```
- Push our changes to our remote repository
```
git push
```
### Merge Develop Branch to Master Branch
- Merge the changes from the develop branch to the master branch
```
git checkout master
git branch (== to be sure we are in master branch ==)
git merge develop --no-ff (== without losing the develop branch history ==)
```
## Feature Branch
### Creating a feature 
- Creating a feature branch from develop branch and switch to feature branch
```
git checkout -b myfeature develop
```
- Finished feature 
- Merge feature to develop
```
git checkout develop (== Switched to branch 'develop' ==)
git merge --no-ff myfeature (== (Summary of changes ==)
git branch -d myfeature (== Deleted branch myfeature ==)
git push origin develop (== Push local to remote develop branch ==)
```
## Release Branch
### Creating a release branch
- Creating a release branch with a tag number
```
git checkout -b release-1.2 develop (== Switched to a new branch "release-1.2" ==)
$ ./bump-version.sh 1.2 (== changes some files in the working copy to reflect the new version ==)
$ git commit -a -m "Bumped version number to 1.2"
```
### Finishing a release branch

- Mmerge release to master
```
git checkout master (== Switched to branch 'master' ==)
git merge --no-ff release-1.2 (== Merge release to master)
git tag -a 1.2 (== set master with 1.2 tag ==)
```
- Merge relese to develop
```
git checkout develop (== Switched to branch 'develop'==)
git merge --no-ff release-1.2 (== Merge release to develop without lossing the history==)
git branch -d release-1.2 (== Deleted branch release-1.2==)
```
## Hotfix Branch
### Creating the hotfix branch 
- Creating the hotfix branch and switch to hotfix branch
```
git checkout -b hotfix-1.2.1 master (== Switched to a new branch "hotfix-1.2.1" ==)
./bump-version.sh 1.2.1  (== changes some files in the working copy to reflect the new version ==)
git commit -a -m "Bumped version number to 1.2.1"
git commit -m "Fixed severe production problem"
```
### Finishing a hotfix branch
- Update master and tag the release on master
```
git checkout master (== Switched to branch 'master' ==)
git merge --no-ff hotfix-1.2.1 (== Merge release to master)
git tag -a 1.2.1 (== set master with 1.2 tag ==)
```
- Update the bugfix in develop
```
git checkout develop (== Switched to branch 'develop'==)
git merge --no-ff hotfix-1.2.1 (== Merge to develop)
```
- Remove the temporary branch
```
git branch -d hotfix-1.2.1 (delete the hotfix branch)
```
