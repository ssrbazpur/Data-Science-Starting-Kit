<h3> GitHub and Git </h3>
<p> Git is a distributed version-control system for tracking changes in source code during software development</p>
<h6>Git Feature Branch Workflow </h6>
<p>
The Feature Branch Workflow assumes a central repository, and master represents the official project history.
Instead of committing directly on their local master branch, developers create a new branch every time they start work on a new feature.
Feature branches can (and should) be pushed to the central repository. This makes it possible to share a feature with other developers without touching any official code — master branch in this case.
Before you start doing anything, type git remote -v to make sure your workspace is pointing to the remote repository that you want to work with.
  </p>
<ol>
  <li>
Start with the master branch and create a new branch
<pre>
git checkout master
git pull
git checkout -b branch-name
</pre>
Provided that the master branch is always maintained and updated, you switch to the local master branch and pull the latest commits and code to your local master branch.
Let’s assume that you want to create a local branch to add a new feature to the code and upload the changes later to the remote repository.
Once you get the latest code to your local master branch, let’s create and checkout a new branch called branch-name and all changes will be made on this local branch. This means your local master branch will not be affected whatsoever.  </li>
  <li> Update, Add, Commit and Push your changes to the remote repository
    <pre>
git status
git add <your-files>
git commit -m 'your message'
git push -u origin branch-name
</pre>

Okay. There is a lot of stuff going on here. Let’s break it down one by one.
Once you’ve made some updates to add the new feature to your local branch-name and you want to upload the changes to the remote branch in order to be merged to the remote master branch later.
git status will therefore output all the file changes (tracked or untracked) made by you. You will decide what files to be staged by using git add <your-files> before you commit the changes with messages using git commit -m 'your message'.
At this stage your changes only appear in your local branch. In order to make your changes appear in the remote branch on Bitbucket, you need to push your commits using git push -u origin branch-name.
This command pushes branch-name to the central repository (origin), and the -u flag adds it as a remote tracking branch. After setting up the tracking branch, git push can be invoked without any parameters to automatically push the new-feature branch to the central repository on Bitbucket. </li>
<li> Create a Pull Request and make changes to the Pull Request </li>
Great! Now that you’ve successfully added a new feature and pushed the changes to your remote branch.
You’re so proud of your contribution and you want to get feedback from your team members before merging the remote branch with the remote master branch. This gives other team members an opportunity to review the changes before they become a part of the main codebase.
You can create a pull request on Bitbucket.
<li>
Now your team members have taken a look at your code and decided to require some other changes from you before the code can be merge into the main codebase — master branch.
  <pre>
git status
git add <your-files>
git commit -m 'your message'
git push
</pre>

So you follow the same steps as before to make changes, commits and finally push the updates to the central repository. Once you’ve used git push , your updates will be automatically shown in the pull request. And that’s it!
</li>
<p>
If anyone else has made changes in the destination to the same code you touched, you will have merge conflicts, and this is common in the normal workflow. You can see here on how to resolve merge conflicts.
Once everything is done without problems, your updates will be finally merged with the central repository into the master branch. Congratulations!
  </p>
