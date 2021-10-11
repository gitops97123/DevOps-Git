## Git 

The linux kernel is an opensource software project of fairy large scope. for most of the lifetime of the linux kernel maintenance(1992-2002), change to the software were passed around as patches and archived files, in 2002, the linux kernel began using a properietary DVCs called bit keeper.

In 2005, the relationship between the community that developed the linux kernel and the commercial company that developed Bitkeeper broke down, and the tools free-of-charges status was revoked. prompted the linux development community to develop their own tool based on source of the lessons they learned while using bitkeeper some of the goal of the new system, were as follows: 

  * Speed 
  * Simple design 
  * Strong support for non-linear develop. 
  * Fully distributed
  * Able to handle largest projects like the linux kernel efficiently (speed and data size)

Git Basic : 

    ibm@led-training:~$ git --help
    usage: git [--version] [--help] [-C <path>] [-c <name>=<value>]
              [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
              [-p | --paginate | -P | --no-pager] [--no-replace-objects] [--bare]
              [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
              <command> [<args>]
    
    These are common Git commands used in various situations:

    start a working area (see also: git help tutorial)
      clone             Clone a repository into a new directory
      init              Create an empty Git repository or reinitialize an existing one

    work on the current change (see also: git help everyday)
      add               Add file contents to the index
      mv                Move or rename a file, a directory, or a symlink
      restore           Restore working tree files
      rm                Remove files from the working tree and from the index
      sparse-checkout   Initialize and modify the sparse-checkout

    examine the history and state (see also: git help revisions)
      bisect            Use binary search to find the commit that introduced a bug
      diff              Show changes between commits, commit and working tree, etc
      grep              Print lines matching a pattern
      log               Show commit logs
      show              Show various types of objects
      status            Show the working tree status

    grow, mark and tweak your common history
      branch            List, create, or delete branches
      commit            Record changes to the repository
      merge             Join two or more development histories together
      rebase            Reapply commits on top of another base tip
      reset             Reset current HEAD to the specified state
      switch            Switch branches
      tag               Create, list, delete or verify a tag object signed with GPG

    collaborate (see also: git help workflows)
      fetch             Download objects and refs from another repository
      pull              Fetch from and integrate with another repository or a local branch
      push              Update remote refs along with associated objects

    'git help -a' and 'git help -g' list available subcommands and some
    concept guides. See 'git help <command>' or 'git help <concept>'
    to read about a specific subcommand or concept.
    See 'git help git' for an overview of the system.


# Step 1: Create a local git repository 

When creating a new project on your local machine using git, you'll first create a new repository (or often, 'repo', for short). 

    ibm@led-training:~$ mkdir project-dir 
    ibm@led-training:~$ cd project-dir/
    ibm@led-training:~/project-dir$ 
To initialize a git repository in the root of the folder, run the git init command: 

    ibm@led-training:~/project-dir$ git init
Initialized empty Git repository in **/home/ibm/project-dir/.git/**

# Step 2: Add a new file to the repo
Go ahead and add a new file to the project, using any text editor you like or running a touch command. `touch file.txt` just creates and saves a blank file named file.txt. 

Once you've added or modified files in a folder containing a git repo, git will notice that  the file exists inside the repo. But, git won't track the file unless you explicitly tell it to. Git only saves/manages changes to files that it tracks, so we’ll need to send a command to confirm that yes, we want git to track our new file.

    ibm@led-training:~/project-dir$ touch file.txt
    ibm@led-training:~/project-dir$ ls
    file.txt

After creating the new file, you can use the git status command to see which files git knows exist.

    ibm@led-training:~/project-dir$ git status
    On branch master
    No commits yet
    Untracked files:
      (use "git add <file>..." to include in what will be committed)
      file.txt
    nothing added to commit but untracked files present (use "git add" to track)
    
    ibm@led-training:~/project-dir$  

What this basically says is, "Hey, we noticed you created a new file called file.txt, but unless you use the 'git add' command we aren't going to do anything with it."

# Step 3: Add a file to the staging environment
Add a file to the staging environment using the git add command. 

    ibm@led-training:~/project-dir$ git add file.txt 
    ibm@led-training:~/project-dir$ git status 
    On branch master

    No commits yet

    Changes to be committed:
      (use "git rm --cached <file>..." to unstage)
      new file:   file.txt

# Step 4: Create a commit
It's time to create your first commit!

Run the command git commit -m "Your message about the commit"

    ibm@led-training:~/project-dir$ git commit -m "Your message about the commit" file.txt 
    [master (root-commit) d2c31f6] Your message about the commit
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 file.txt
    
    ibm@led-training:~/project-dir$ git status
    On branch master
    nothing to commit, working tree clean

# Step 5: Create a new branch
Now that you've made a new commit, let's try something a little more advanced.

Say you want to make a new feature but are worried about making changes to the main project while developing the feature. This is where git branches come in. 

    ibm@led-training:~/project-dir$ git branch
    * master

# Step 6: Create a new repository on GitHub
If you only want to keep track of your code locally, you don't need to use GitHub. But if you want to work with a team, you can use GitHub to collaboratively modify the project's code.

To create a new repo on GitHub, log in and go to the GitHub home page. You can find the “New repository” option under the “+” sign next to your profile picture, in the top right corner of the navbar:

![new repository](https://github.com/gitops97123/gitOps/blob/main/icons/01.png?raw=true)

After clicking the button, GitHub will ask you to name your repo and provide a brief description:

![new repository](https://github.com/gitops97123/gitOps/blob/main/icons/02.png?raw=true)

When you're done filling out the information, press the 'Create repository' button to make your new repo.

GitHub will ask if you want to create a new repo from scratch or if you want to add a repo you have created locally. In this case, since we've already created a new repo locally, we want to push that onto GitHub so follow the '....or push an existing repository from the command line' section: 

![new repository](https://github.com/gitops97123/gitOps/blob/main/icons/03.png?raw=true)

    ibm@led-training:~$ git clone git@github.com:gitops97123/project-dir.git
    Cloning into 'project-dir'...
    warning: You appear to have cloned an empty repository.
    ibm@led-training:~$ ls
    project-dir

![new repository](https://github.com/gitops97123/gitOps/blob/main/icons/04.png?raw=true)

Now, Go to the **Deploy keys** sections, and click on **Add deploy key** 
lets have a look where you can add & deploy the public keys. 
Copy the public key to add deploy keys and click on "**Add key**" 

    ibm@led-training:~$ cat ~/.ssh/id_rsa.pub
    ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABgQCxQZ/GUJsUqQ1tjJZ1cFJ1HWBzwjymZSYQ65PX5q0QBIIfK7fytIcp1aZokl/ZWDkgcj4Xn2Vd8MSneAl/PNxoovXtBrLvvbQTOCXV9e/pd47Jv6ZjzooMrKyjACH6WNC8Rzkju1AgWHsmlz3w3VgMO/G6vG019aqA8Fl5hbxdvLCCoePsYwjzJXlK8DbBoWnKbfy95OM3min5FQQiKKULPXAh9aOkLlU9B4GRXfVZnEKrSkHxNMRux6+avqe/9/jOh0JVCo6LyTyvKDyekfpLQjSXoE8TMa5G9IiYBnZZv+LoMEmS+WxhgpRjRr0jP1UYbZhBvFs4wisSSyJQrB2VnJjPVWyTi1YglSazDwAkEpREIEKKHEg/Tc66tVNoEg6XRWpCkzGPqpACTshXuE8Yr4hrj0FnP89pCwwLWRaetCU9VN4oa+9D0S+nxnrmrIUcXixGZmoxKAUM8Id8qWtBwyi4RVhIhUI5iikbcJNSojpG4z9oAeJa3ryhRssd/3E= ibm@led-training
![new repository](https://github.com/gitops97123/gitOps/blob/main/icons/06.png?raw=true)

# Step 7: Push a branch to GitHub
Now we'll push the commit in your branch to your new GitHub repo. This allows other people to see the changes you've made. If they're approved by the repository's owner, the changes can then be merged into the primary branch.

To push changes onto a new branch on GitHub, you'll want to run git push origin yourbranchname. GitHub will automatically create the branch for you on the remote repository:

    git@led-training:~/project-dir$ touch file.md
    git@led-training:~/project-dir$ git add file.md 
    git@led-training:~/project-dir$ git commit -m "add new file" file.md 
    [master (root-commit) 28f7735] add new file
    1 file changed, 0 insertions(+), 0 deletions(-)
    create mode 100644 file.md

    git@led-training:~/project-dir$ 
    
    git@led-training:~/project-dir$ git push origin 
    Enumerating objects: 3, done.
    Counting objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 214 bytes | 214.00 KiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0)
    To github.com:gitops97123/project-dir.git
    * [new branch]      master -> master
    
    git@led-training:~/project-dir$ 

Now, Go to your web browser and refresh the repository and verify your data.


![new repository](https://github.com/gitops97123/gitOps/blob/main/icons/07.png?raw=true)



