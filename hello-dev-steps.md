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

>This offers us an opportunity to exercise the command and to demonstrate how Go expects to have its environment structured.

**Prerequisites:**
* Go installed and $GOPATH configured
* Github repo created

```bash
go get github.com/GITHUB-USERNAME/GITHUB-REPO
```
This will clone your repo in the correct spot within your Go environment:

`$GOPATH/src/github/GITHUB-USERNAME/GITHUB-REPO`

**Error when go getting an empty repo**<br/>
This command will attempt to build the Go source files in a repository.  Since all we have created is a default `README.md` and a Go-flavored `.gitignore`, `go get` will report an error:

`no buildable Go source files in /$GOPATH/src/github/GITHUB-USERNAME/GITHUB-REPO`

However, if you navigate to where the repo was cloned, you will see that the contents were successfully cloned:
```bash
$ cd $GOPATH/src/github.com/GITHUB-USERNAME/GITHUB-REPO
$ ls -al
total 16
drwxr-xr-x   5 you  staff  170 Nov  8 18:47 .
drwxr-xr-x   6 you  staff  204 Nov  8 18:47 ..
drwxr-xr-x  12 you  staff  408 Nov  8 18:47 .git
-rw-r--r--   1 you  staff  266 Nov  8 18:47 .gitignore
-rw-r--r--   1 you  staff   25 Nov  8 18:47 README.md
```

At this point we are ready to start writing Go!

#### Or are we?
>There is a host of tools that make writing Go far more enjoyable.  Do we need to walk the reader through installing them?  Should we also take a moment to talk about editors?

>**Tools:**
>* goimports - formats source and manages imports
>* gocode - supports autocomplete
>* godef - enables jumping to definition
>* golint - code linting
>* vet - code quality inspection
>* godep - dependency management & vendoring

>**Editors:**
>* Atom - OSX, Windows, Linux; go-plus plugin
>* Sublime Text - OSX, Windows, Linux; GoSublime plugin
>* Vim - sux on windows; vim-go plugin
>* Emacs - runs everywhere; go-mode (config and usage not for the feint of heart)

### Hello, World!

Create a new file called `main.go`:

```golang
package main

import (
	"fmt"
	"net/http"
	"os"

	"github.com/codegangsta/negroni"
)

func main() {
	port := os.Getenv("PORT")
	if len(port) == 0 {
		port = "8080"
	}

	mux := http.NewServeMux()
	mux.HandleFunc("/", hello)

	n := negroni.Classic()
	n.UseHandler(mux)
	hostString := fmt.Sprintf(":%s", port)
	n.Run(hostString)
}

func hello(res http.ResponseWriter, req *http.Request) {
	fmt.Fprintln(res, "Hello from Go!")
}

```


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