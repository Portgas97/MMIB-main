# MMIB-main
Microservices-based My Message in a Bottle application

## Pushing updates
So you've made changes in the submodule's repository and committed them in its repository. If you now do a git status in the main repository, you'll see that the submodule is in the list Changes not staged for commit and it has the text (modified content) behind it. This means that the code of the submodule is checked out on a different commit than the main repository is pointing to. To make the main repository point to this new commit, you just add this change with git add and then commit and push it.

## Keeping your submodules up-to-date
If someone updated a submodule, the other team-members should update the code of their submodules. This is not automatically done by git pull, because with git pull it only retrieves the information that the submodule is pointing to another commit, but doesn't update the submodule's code. To update the code of your submodules, you should run:

git submodule update

To make it easier:

git pull --recurse-submodules

This will pull the main repository and also it's submodules.

And you can make it easier with aliases:

git config --global alias.clone-all 'clone --recurse-submodules'
git config --global alias.pull-all 'pull --recurse-submodules'
