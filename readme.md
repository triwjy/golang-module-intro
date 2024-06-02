# Go Module

## Creating a module

Module in golang is similar to project, where when we just started to create a project we initiate it with `go mod init <module name>`. By executing this command, golang will create `go.mod` file that contain the name of the module and golang version information.

Example content of `go.mod`:

```
module belajar-golang-standard-library

go 1.21.4
```

By using _go module_ we no longer need to save the project folder inside the `GOPATH`.

### Steps to create a new project:

- Create a new github repository
- Create a local folder preferably use the same name as the repo name,
- Inside the folder: `go mod init github.com/<path to repo>`
- Git checkout -b <your-branch>
- Write your code
- Git init
- Git add
- Git commit

## Releasing a module

Go-Lang also integrated with Git, to release a module, we just need to create a `Tag` in Git.
Example on creating a tag:

```
git tag v1.0.0
git push origin v1.0.0
```

## Adding dependency

To add dependency to your project(module) as simple as: `go get <module name>` (the module name in go.mod).  
If you use private repo, consult `https://go.dev/doc/faq#git_https` where you can edit`~/.netrc`

## Upgrading module

To release a new version of your module, you just need to create a new git tag.

- edit your code
- git add & git commit your code
- git push
- git tag <new version>
- git push origin <new version>

## Upgrading dependency

After the module is upgraded, it is time to update the dependency from the app side.  
It is as easy as editing the tag version inside the go.mod for that dependency, then execute `go get`

## Major upgrade

Major upgrade is usually happen because there's a change in our code that's causing it not backward compatible (for example due to security concern).  
If this cannot be avoided, the best strategy is to change the module name (for example by adding `/v2` as suffix).  
You also need to change the tag when pushing into remote repo.  
Now, every app that wants to use the new major version, it needs to execute the `go get <new major version name>`. Don't forget to update the import statement to use the new name as well.
