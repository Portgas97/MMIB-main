# MMIB-main
Microservices-based My Message in a Bottle application

## Add a submodule
If you want to add a microservice (hence a submodule), you have to run the command:

  <code>git submodule add -b \<branchName\> \<repoURL\></code>

## Pushing updates
So you've made changes in the submodule's repository and committed them in its repository. If you now do a git status in the main repository, you'll see that the submodule is in the list Changes not staged for commit and it has the text (modified content) behind it. This means that the code of the submodule is checked out on a different commit than the main repository is pointing to. To make the main repository point to this new commit, you just add this change with git add and then commit and push it.

## Keeping your submodules up-to-date
If someone updated a submodule, the other team-members should update the code of their submodules. This is not automatically done by git pull, because with git pull it only retrieves the information that the submodule is pointing to another commit, but doesn't update the submodule's code. To update the code of your submodules, you should run:


  <code>git submodule update --remote</code>


To make it easier:


  <code>git pull --recurse-submodules</code>


This will pull the main repository and also it's submodules.

And you can make it easier with aliases:


  <code>git config --global alias.clone-all 'clone --recurse-submodules'</code>


  <code>git config --global alias.pull-all 'pull --recurse-submodules'</code>
  
  
## Configuration
Each micro-service should have a single configuration file, placed inside the main project root, with the name <microservice_name>_ms.conf. An example of this can be found in the project root.

## Development
The project structure should be the following:

## Build and run
Application is built with docker-compose. To build the environment you have to run

  <code>docker-compose build</code>

To startup application you can issue the following command:

  <code>docker-compose up</code>

Application Environment
The default application environment for this application is production.

