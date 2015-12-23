# Getting Started
## Installation
### OSX via Homebrew
#### Install Homebrew
First, we need to install the command line tools for
XCode. Open a Terminal window and enter the following:
```bash
  xcode-select --install
```

Install Homebrew:
```bash
  ruby -e “$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)”
```

Verify successful install:
```bash
  brew doctor
```

Install [Homebrew Cask](http://caskroom.io):
```bash
  brew install caskroom/cask/brew-cask
```

#### Install Git
Werdz
```bash
  brew install git
```

#### Install Go
More Werdz
```bash
  brew install go
```

*There will likely be a separate section for configuration your Go environment. Refer to: https://golang.org/doc/install*

#### Install Vagrant
Vagrant is...werdz
```bash
  brew cask install vagrant
```

#### Install VirtualBox
VirtualBox is...werdz
```bash
  brew cask install virtualbox
```

#### Install Lattice
**(OSX Section, not specific to Homebrew.  Prerequisites are Git, Vagrant, VirtualBox)**

Download a Lattice release bundle from the [Github Releases](https://github.com/cloudfoundry-incubator/lattice-release/releases) page.  Once you've downloaded a bundle, unzip it and `vagrant up` in the vagrant directory:

```bash
unzip lattice-bundle-VERSION.zip
cd lattice-bundle-VERSION/vagrant
vagrant up
```

Then bring up the Vagrant box:
```bash
vagrant up --provider virtualbox
```
##### Install ltc (The Lattice CLI)

The command line tool `ltc` can be downloaded from the cluster:

```bash
$ curl -O http://receptor.local.lattice.cf/v1/sync/osx/ltc
$ chmod a+x ltc
$ mv ltc /usr/local/bin
```

*Reference: http://lattice.cf/docs/getting-started/*


#### Install Docker

##### Via Homebrew

Ensure that VirtualBox is installed and that you've recently updated your homebrew installation with `brew update && brew upgrade`.

```
$ brew install docker docker-machine<br>
$ docker-machine create --driver virtualbox default<br>
$ eval "$(docker-machine env default)"<br>
```
To test your docker installation, try running:

`$ docker images`

You should see output similar to

```
$ docker images
REPOSITORY            TAG                 IMAGE ID            CREATED             VIRTUAL SIZE

$
```

###### Possible version mismatch issue
It is possible that you might encounter an error when trying to run any docker command:

```
$ docker images
Error response from daemon: client is newer than server (client API version: 1.21, server API version: 1.20)
$
```

This is easily remedied by upgrading your docker machine instance:

`$ docker-machine upgrade default`

