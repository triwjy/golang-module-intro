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
