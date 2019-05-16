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

## Git Flow

1. <b> Successful Git Branching Model</b> [more](https://nvie.com/posts/a-successful-git-branching-model/) [PDF](https://github.com/ronnytorresmtz/tutorials/blob/master/Git-branching-model.pdf)
2. <b> Prevet Commits on Master Branch </b> [more](https://stackoverflow.com/questions/40462111/git-prevent-commits-in-master-branch)
3. <b> Git Guide from Attlasian </b> [more](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)
4. <b> Git Cheat Sheet </b> [more](https://github.com/ronnytorresmtz/tutorials/blob/master/atlassian-git-cheatsheet.pdf)
5. <b> Git Basics Instructions </b>

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

