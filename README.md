# Mark3 repo manifest

This repository contains the git repository manifest that can be initialized
and managed using Google's [Repo](https://source.android.com/setup/develop/#repo)
tool.  

This tool gives developers the ability to incorporate a variety of components together
from different sources, as independent Git repositories.  It's an effective means
for managing large projects, as demonstrated by its usage in AOSP.  While most 
Mark3 projects will be exponentially smaller than AOSP, many will still involve
tools/source/libraries based on multiple Git repos.  As a result, using Repo makes
sense, particularly if you want to avoid relying on Git's submodule functionality, 
or wish to integrate with the Gerrit code review system.

## Requirements

Before the Mark3 repo manifest can be used, the developer must first install the
Repo tool.  See the instructions [Here](https://source.android.com/setup/build/downloading)
for details and dependencies.

## Initializing the repo client

(Note - these instructions are largely based on the instructions [Here](https://source.android.com/setup/build/downloading))

Once the Repo tool has been initialized, it's straightforward to initialize the 
Mark3 repo manifest at a specific location:

1) Create a directory where you wish to initialize your repository.
```
    $ mkdir mark3-code
    $ cd mark3-code
```
2) Set Git configuration 
```
    $ git config --global user.name "Your Name"
    $ git config --global user.email "your@email.com"
```
3) Run repo init in the target directory
```
    $ repo init -u ssh://git@github.com/moslevin/mark3-repo --no-clone-bundle
``` 
## Downloading code

An initialized repository client can download and synchronize the individual git
repositories specified in the manifest by running the following command:
```
    $ repo sync
```
## More information

See the Android project's documention for Repo [here](https://source.android.com/setup/develop/repo)

