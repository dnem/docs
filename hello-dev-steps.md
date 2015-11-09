# Development Steps for Hello World
Outline of the steps we took to develop the hello world end-to-end example.

## Local Development

### Sign Up for Github
May need to walk the user through the Github sign-up process...

### Create Github Repo
>Doing this first accomplishes 2 things:
>1. Get Github's default `.gitignore` file for Go
>2. Repo can be cloned via `go get` and placed in the correct location

1. Click on the New button
2. Provide repo name
3. Provide an optional description
4. Select Public radio button (default)
5. Check the `Initialize this repository with a README` checkbox
6. Click on the `Add .gitignore` button and choose "Go" in the dialog box
7. Click the `Create repository` button

### Clone the new repo
>Normally, you would clone your repo via `git clone git@github.com:GITHUB-USERNAME/GITHUB-REPO.git`.  However, Go provides `go get`, a command that will clone a specified Go project and install it properly in your $GOPATH.

**Prerequisites:**
* Go installed and $GOPATH configured
* Github repo created

```bash
go get github.com/GITHUB-USERNAME/GITHUB-REPO`
```
This will clone your repo in the correct spot within your Go environment:

`$GOPATH/src/github/GITHUB-USERNAME/GITHUB-REPO`

**Error when go getting an empty repo**<br/>
This command will attempt to build the Go source files in a repository.  Since all we have created is a default `README.md` and a Go-flavored `.gitignore`, `go get` will report an error:

`no buildable Go source files in /$GOPATH/src/github/GITHUB-USERNAME/GITHUB-REPO`



### VCAP & Environment

## Wercker & Docker (recommended)

### Local Wercker Steps

### Remote Wercker Steps

#### Deploy to DockerHub

### Deploy Docker on Lattice

## Alternate (Local) Development Strategy
This is an alternate workflow that deploys to Lattice by creating droplets.

### Build Droplet

### Deploy Droplet on Lattice