#Git Workshop

##Goals:
####Install Git
- Install Git onto your computer
- Set up Git configuration settings

####Create a Github Account
- Create new Github account
- Quick overview of Github

####Create Repository
- Learn how to create own repository on Github 
- Initialize repository on computer 
- Set remote repository to Github repo URL 
- Add contents of new repository to commit
- Push up to master branch of Github repository

####Cloning a Repository
- Clone code from Github 
- Create new branch
- Change code around a bit
- Learn how to add files to staging area
- Commit on new branch
- Push code back to Github

##First Steps:
Install Git:

    Go to `http://git-scm.com/downloads`
    Follow instructions regarding Git installation (should be included in Git download package)
    Set up your Git configuration settings via instructions at `https://help.github.com/articles/set-up-git`
    IMPORTANT: When configuring your Git email settings, MAKE SURE IT MATCHES THAT OF YOUR GITHUB ACCOUNT EMAIL / EMAIL YOU ARE PLANNING TO USE FOR GITHUB ACCOUNT
    Ignore the `Password Caching` session for now - you can choose to do this later.

Create New Github Profile:

	Go to https://github.com/
	Create a new account (username, email, password)
	When you confirm your account, it will redirect to the home page
	Click on the '+' sign next to your username in top right
	Select 'New Repository' 
	Give the repository the name 'git-todo'

Open terminal and follow instructions:

    cd ~/Desktop
    mkdir git-todo
    cd git-todo

    touch README.md
    git init
    git add README.md
    git commit -m "initial commit"
    git remote add origin <paste http:// link here from Github>
    git push origin master
    
###What Happened?
- `cd ~/Desktop` will change directory into our 'Users/<username>/desktop' directory
- `mkdir git-todo` will create a new folder called 'git-todo' on your Desktop
- `git init` creates a new repository in our `git-todo` directory. `cd git-todo` changes the directory into the `git-todo` directory. Think of it as going down one level.
- `touch README.md` generates a markdown file that is called README. 
- `git init` initializes, or generates, a new `.git` file. Think of a `.git` file as the memory store at the root of a directory. The logic that stores your repository data as well as the synchronization between your remote repositories is encapsulated in this `.git` file.
- Before you can commit new files, you have to "stage" them by adding them to a staging directory. You do this by `git add README.md`. You can also add all new/updated files in current directory by doing `git add .`, and if you also need to remove files that were deleted, you do `git add -A`
- Once all the previous steps are finished, you commit the staging file via `git commit -m "initial commit".
- In order to push these files up to your Github account, you need to create a repository on Github.com
- Go to the main Github page, click on the '+' sign, and select `New Repository`. Then name the repository `git-todo`. Then once you have created the repository, copy the HTTPS clone URL in the middle of the screen.
- Add your remote via `git remote add origin https://github.com/<your-username>/git-todo.git`
- Finally, push up to your remote via `git push origin master`.

##Next Steps:
- In this next step, we will clone a repository to our desktop, modify the file contents inside of the repository, commit those changes, and push back up to the `solutions` branch of the Github repository.
- Go to `https://github.com/irmiller22/git_workshop_test`.
- FORK this repository -- once the page reloads, the URL for your repository should be `https://github.com/<your-username>/git_workshop_test`.
- Clone your `git_workshop_test` repository via the HTTPS clone url option in the lower right hand corner of the Github repository screen.
- Switch over to your Terminal. 
- If you are not at your Desktop path, change directory via the following command: `cd ~/Desktop`.
- Then type in: `git clone <paste Github HTTPS URL here>`.
- Once completed, type `ls` to show all files/folders on your Desktop directory. You should see the `git_workshop_test` repository here.
- Change directory into the repo via `cd git_workshop_test`
- Open up the `assignment.md` file, and follow instructions there.

##Cloning:
`cd` into a the directory you want your project to live in.

On Github, go to the repository you want to contribute to and copy the link on the right hand side of the page.

Back in terminal, and type: `git clone <paste http:// link here from Github>`

(Note, if this project is something sustantial, say an open source project that you would like to contribute to, it's best practices to `Fork` the repo to your page and then clone that fork. A `fork` is basically copying and pasting the repo.)

Once you've cloned the repo, make the changes you want and then, just like when you initialized a new repo above, stage, commit, and push your changes:

    git add <file you've changed>
    git commit -m "these are the changes I've made"
    git push origin master

##Branching:
Another best practice technique is to make every body of work a separate branch. So far, we've been pushing to the `master` branch. You can create your own branching off of the `master` branch and do you work on that.

While on master, before you begin working, type:
`git checkout -b <your-branch-name>`

Do your work on this branch, and while on this branch, be sure, like above to stage, commit, and, if you want your teammates to see your work, push your changes up to Github on your new branch:

    git add <file you've changed>
    git commit -m "these are the changes I've made"
    git push origin <your-branch-name>

Note the last command is pushing the changes up to your new branch, not master. 

##Merging
When you're done with your work on your new branch, you may want to merge it into master. There are two ways to do this, either locally (through git on your computer) or remotely (on Github).

###Locally
Move onto the branch that you want to merge <strong>into</strong>, in this case, `master`: `git checkout master`.
Then, merge your new branch into master: `git merge <your-branch-name>`
Now, master is up to date with your changes on your local repo, and you can `push` them up to Github.

###On Github
One arguably better way to handle merging when dealing with a project that multiple people work on is to do all of your work on your new branch, push it up to Github, and then submit a `Pull Request` on the site. Here, others can see the merge, and Github can check to make sure there aren't any conflicts.

##More Commands
Here are some other commands to go along with the basic ones we've already covered:

`git status`: at any point of your work, if you want to see the status of your repo, type `git status` when you're within your project directory to see which files are staged or unstaged.

`git pull`: when you're working with other people on a project that's living on Github, most likely they'll be making changes to the code and pushing it up. To bring those changes down to your local repo (on your computer), you will need to `pull` them.

`git stash`: let's say you've made changes since then that you don't want anymore. Instead of going into your text editor and manually finding the change, you can `stash` them and they'll be deleted. Your file will go back to how it was when it was staged last. This is handy, but make sure you absolutely want to do away with your changes before you do this!

##OTHER RESOURCES:
###Getting Started
- [Getting Started 1](http://git-scm.com/book/en/Getting-Started-A-Short-History-of-Git)
- [Getting Started 2](http://git-scm.com/book/en/Getting-Started-About-Version-Control)

###Basics of Git
- [Git Basics 1](http://git-scm.com/book/en/Git-Basics-Recording-Changes-to-the-Repository)
- [Viewing The Commit History](http://git-scm.com/book/en/Git-Basics-Viewing-the-Commit-History)
- [Undoing Things](http://git-scm.com/book/en/Git-Basics-Undoing-Things)
- [Remotes](http://git-scm.com/book/en/Git-Basics-Working-with-Remotes)
- [Branches](http://git-scm.com/book/en/Git-Branching-What-a-Branch-Is)
- [Merging](http://git-scm.com/book/en/Git-Branching-Basic-Branching-and-Merging)
- [Branch Management](http://git-scm.com/book/en/Git-Branching-Branch-Management)
- [Workflows](http://git-scm.com/book/en/Git-Branching-Branching-Workflows)
- [Rebasing](http://git-scm.com/book/en/Git-Branching-Rebasing)

###Additional Resources
- [Git Guide](http://rogerdudler.github.io/git-guide/)
- [Think like a git](http://think-like-a-git.net/)
- [Git Branching](http://pcottle.github.io/learnGitBranching/)
- [Visual Git](http://marklodato.github.io/visual-git-guide/index-en.html)
- [Git ready](http://gitready.com/)
- [Git Immersion](http://gitimmersion/)
