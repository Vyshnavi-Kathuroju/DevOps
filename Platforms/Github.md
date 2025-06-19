# Getting Started with Github

Once you have a github account, 

1. Create a new repository
2. Add a README.md file
3. Create structure to the repo

## Github Website

It starts with creating a repository to store your code and project.

As I am exploring Github from a beginner's perspective, I started with Github website to create a respository, Add a README file and high level directories, all within the website itself.

1. Use `New` option on the dashboard to create a new respository
   
2. On the repository page, use `Add file` > `Create new file` to add README.md and `Commit changes`.
   - Github has an editor that will allow you to create and edit files on the website itself.
   - If you are new to Markdown Syntax and Styling, the editor will have an icon at the bottom right to the relevant github docs.
     
3. Create a high level structure for your repository.
   - This involves creating directories and files within.
   - Use `Add file` > `Create new file` > `directory_name\` to create a directory.
   - When you add a `\` to the the end of the filename, it will be treated as directory.

I have currently created four folders in my repo to for a high level structure. Everything was done within the Github website itself at this point. I did not have to setup or install anything on my local system. But I see that I have to use a lot of clicks to get the work done. This approach is not feasible for complex development work. After working for a couple of hours, this process seems tedious. As I know I have to repeat this process on a daily basis, I need a local setup to build my project going forward.

## Git Command Line

### Getting Started

Now that the basic project structure is already created through Github Website, a [local development environment](</Tools/Local Development Environment.md>) is needed to work with it locally. 

Before anything else, the project that already exists on the remote repo needs to be copied locally. 
- _Using User Interface (UI)_. One option to download the ZIP file using Github Website or through Github Desktop.
- _Using Command Line Interface (CLI)_. A more interesting option and a developer way of doing this is to do a `git clone` using the Git CLI.

[What is Git?](/Tools/Git.md)

Once you have Git installed on your system, you can start working with your project on Github.

`git clone` will allow you to copy the repo locally.

```
git clone [URL]
```

To make sure you have the latest changes or commit locally, first do a `git status` to see if there are any changes made locally and then `git fetch` to see any remote changes.

```
git status
git fetch
```

`git fetch` will not return any output if there are no latest changes on the remote repo.

You can also use `git log` to see the local commit history.

```
git log --one-line
```

`git merge` will merge the remote repo changes locally

```
git merge origin/main
```

Once you are have the latest copy of the repo, you can start to make changes locally - add files, update files or delete files.

After you have made the required changes locally, its time to `commit` and `push` the changes.

Commit is like a checkpoint. When you create a commit, a checkpoint is created, enabling you to revert back to this commit incase you need to undo the changes. 
We usually create a commit 
- once we have made changes that we are ready to share with others.
- when you want to save one approach to the problem
- or just save your progress so far

`git add -A` adds all the changes to the Staging Area

```
git add -A
```

To unstage the changes use `git reset`
```
git reset
```

`git commit` creates a local commit.

```
git commit -m '[commit message]'
```

`git push` will upload the local changes to the remote repo.

```
git push
```

### Authentication

If you have not authenticated to your Github from Git CLI and perform `git push`, you will be prompted with different Sign-in options.

One option is a browser based authentication. If you choose this, new browser tab will be opened with instructions and asking for permission to allow Git Credential Manager to manager you sign-in. You can later view this integration under 

_Settings > Integrations > Applications > Authorized OAuth Apps_.

Another option is to use SSH Key based authentication. You can use this SSH Key for signing commits. Once you generate SSH key pair, add the public key under 

_Settings > Access > SSH and GPG Keys > New SSH Key> Authentication Key_.

### Branch protection rules

If you tried to make unsigned commit, you will observe that it will allowed. If you want block any unsigned commits to your repo, you need to specify this under 

_Repository Settings > Code and automation > Branches > Branch protection rules > Add branch ruleset > Check Require signed commits > Save changes_

### Signing Commits

When you push the commits without signing, the commit does not have a _Verified_ tag if the vigilant mode is not enabled.
If the `vigilant` mode is enabled, any unsigned commits will be shown as `Unvertified`.

Enable _vigilant mode_ under _Settings > SSH and GPG Keys > Vigilant mode_.

To verify a commit, you need to use SSH Keys or GPG Keys for signing. Refer to the documentation for generating such keys.

Once you have generated the public/private key pair, you need to configure Git CLI to use this key for signing commits and also add the public key to Github so that it can be verified. _New SSH Key > Signing Key_.

To sign a specific commit,
```
git commit -S -m 'Signed Commit'
```

To automatically sign all the commits,
```
git config --global commit.gpgsign true
```

Any commits you make after this point will be tagged as `Verfied`.























