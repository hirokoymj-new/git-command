## Combining Git commits with squash (before pushing)

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

## Combining Git commits with squash after pushing remote

Combining your commits in the local first.

```js
git rebase -i HEAD~2
```

**Before**

```js
//git log
commit 1a7252d6e70116a2f283d5c13439b1bdf3841010 (HEAD -> force-test, origin/force-test)
Author: Hiroko Yamaji <hiroko@hirokoymj.com>
Date:   Fri Dec 17 15:02:35 2021 +0900

    bbb

commit f2d096bf287676b9351a8cb9e4dd4a9773e09cea
Author: Hiroko Yamaji <hiroko@hirokoymj.com>
Date:   Fri Dec 17 15:02:21 2021 +0900

    aaa

```

**After**

```js
// git log
commit f6be1fa48f869512b4daf28a9bc729a41f0481ab (HEAD -> force-test)
Author: Hiroko Yamaji <hiroko@hirokoymj.com>
Date:   Fri Dec 17 15:02:21 2021 +0900

    combined two commits.
```

Then push your branch with `--force` option.

```js
git push origin test --force
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

- Run `git commit --amend`.

```js
git commit --amend
```

- In Editor mode you can change a current message.

```js
comment 1

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# Date:      Fri Dec 17 11:51:29 2021 +0900
#
```

squash test 1
squash test 2
