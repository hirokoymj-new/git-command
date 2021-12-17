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

## Pull

Get the latest code from remote repository so your local repository could be updated. When your co-workers update a master branch, you should get the latest one!

```js
git pull master
```

## Stash

Using `stash` command, you can hold your all changes temporary and makes clean working directory. So you can merege the latest master into your own branch.

```js
git stash //-----> Hold all your changes and your branch becomes clean.
git merge master //---> you can merge the latest master here!
git stash apply	// ---> Changed back to your changes.
```

## Log

Trying to see the git log.

```js
git log ---graph --oneline
```

## Remove remote repository

```js
git remote origin [remote-repo-name]
```

## Show remote repository in your local

```js
git remote show origin

git fetch
git checkout test
```

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

git commit --amend -m "new message"

## Modify commit message

when you have typo in a commit message, you can fix using below command then push again.

```js
git commit --amend -m "new message"
```

## git reflog

- listed all the tips of branches

```js
// checking all logs
git reflog

//you can rollback at hash number 12345
git reset --hard 12345
```

<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />

## commit test 1-1

## commit test 1-2

## commit test 1-3
