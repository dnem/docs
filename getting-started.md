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

The command line tool `ltc` can be downloaded from teh cluster:

```bash
$ curl -O http://receptor.local.lattice.cf/v1/sync/osx/ltc
$ chmod a+x ltc
$ mv ltc /usr/local/bin
```

*Reference: http://lattice.cf/docs/getting-started/*


