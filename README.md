## Combining Git commits with squash

1. Try to four commits to one.

```js
git rebase -i HEAD~4
```

1. Editor mode. Replace `pick` to `squash` and save the file with `ESC + WQ!`.

**Before**

```js
pick 02d2eb1 This is the final commit.
pick 577eada the first commit
pick 5cf4b91 the second commit
pick 0bac4a7 third commit
```

**After**

```js
pick 02d2eb1 This is the final commit.
squash 577eada the first commit
squash 5cf4b91 the second commit
squash 0bac4a7 third commit
```

3. Editor mode again. Update your commit comment. `#` will be ignored.

```js
The final commit message.
```

4. Show git log and see if you can see one commits.

```js
git log --oneline
```

<hr />

## Merge

Trying to merge `test-branch` to `master` branch.

1. Check if you are currently master branch.
   ```js
   git branch
   ```
2. Merge `test-branch` to `master`
   ```js
   git merge test-branch
   ```
3. Push the upated master branch to remote repository
   ```js
   git push origin master
   ```

<hr />

## Pull

Get the latest code from remote repository so your local repository could be updated. When your co-workers update a master branch, you should get the latest one!

```js
git pull master
```

<hr />

## Stash

Using `stash` command, you can hold your all changes temporary and makes clean working directory. So you can merege the latest master into your own branch.

```js
git stash //-----> Hold all your changes and your branch becomes clean.
git merge master //---> you can merge the latest master here!
git stash apply	// ---> Changed back to your changes.
```

<hr />

## Log

Trying to see the git log.

```js
git log ---graph --oneline
```

<hr />

## Delete Remote Branch

```js
git push origin --delete <remote branch name>
```

```js
hiroko@owners-MacBook-Pro git-command % git push origin --delete demo
To https://github.com/hirokoymj/git-command.git
 - [deleted]         demo
```

<hr />

## Delete Local Branch

```js
git branch -D <branch name>
```

<hr />

## Show remote repository in your local

```js
git remote show origin

git fetch
git checkout test
```

<hr />

## git reset HEAD^

https://dzone.com/articles/git-reset-head

## Rename local branch

If you want to rename a branch while pointed to any branch, do:

```js
git branch -m <oldname> <newname>
```

If you want to rename the current branch, you can do:

```js
git branch -m <newname>
```

## Switching current repo to another one

```js
git remote set-url origin <new repository> to update your config
```

git remove -v to see your current repository

## Undo your commit

```js
git reset HEAD~
```

## Checkout remote branch

Use `checkout` instead of `git pull branch-name`

```js
git checkout [remote branch name]
```

## Modify a commit message

<<<<<<< HEAD
- Run `git commit --amend`.
=======
## Modify a commit message

1. Run `git commit --amend`.
>>>>>>> db578f79e9a6c5fffb6be71b9de740629559a738

```js
git commit --amend
```

<<<<<<< HEAD
- Changes to an editor mode so you can edit a current message.
=======
1. Changes to an editor mode so you can edit a current message.
>>>>>>> db578f79e9a6c5fffb6be71b9de740629559a738

```js
comment 1

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Fri Dec 17 11:51:29 2021 +0900
#
<<<<<<< HEAD
```

<hr >
=======

```
>>>>>>> db578f79e9a6c5fffb6be71b9de740629559a738
