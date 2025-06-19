# What is Git ?

We generally learn `Git` in the context of Github or other Code Repository. Git is basically a `Distributed Version Control System` that enables the modern software development process with tens to hundreds to thousands of developers collaborating and contributing on a project.

[Version Control System](</Technology/Version Control System.md>)

Git as a technology enables us to manage and track the progress and history of our project.

### So what does Git help us do exactly ?

#### _There is a remote repository that you need to clone on your system locally_

When you have a remote repo that need to copy locally, perform `git clone`. 
 
``` 
git clone {URL}
```

#### _You made changes to the local copy and now you want to save them_

Once you made a few changes to the local copy of the code, save them using `git commit`.

```
git commit -m 'Git.md file has been added'
```

#### _Upload the changes to the remote repo_

When you commit the code, the changes are still sitting on you local system. To upload the changes to the remote repository, do `git push`

```
git push --set-upstream origin main
```

#### _How does a development team work with Git ?_

The above command will push the code to the main branch of the repo. If you are working with a different branch, you need to set the origin accordingly. 

Within an enterprise, you always, work with a branch. No one touches the sacred `master` branch. 

When a team member has a feature to implement or a bug to fix, they always create a new branch and work with it till they can produce a successful build with that branch. When you know that the code works, a `pull request` is raised to `merge` the code into the master branch. Onces the changes have been merged, you can see your changes in the main/master branch. Also the `pull request` or `merge` will be used to as trigger for the `Continous Integration and Continous Delivery (CI/CD)` pipelines and automation.










