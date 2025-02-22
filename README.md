# Betty

[![Build Status](https://travis-ci.org/holbertonschool/Betty.svg?branch=master)](https://travis-ci.org/holbertonschool/Betty)

### Installation

Run the script `install.sh` with **sudo privileges** to install `betty-style` and `betty-doc` on your computer, along with the  following manuals:

 * _betty(1)_
 * _betty-style(1)_
 * _betty-doc(1)_

### Documentation

Please visit the [Betty Wiki](https://github.com/holbertonschool/Betty/wiki) for the full specifications of Betty coding and documentation styles.

You'll also find some references and some tools for common text editors such as Emacs and Atom.

### Usage

Run the following command to check if your code/doc fits the Betty Style (mostly inspired from the Linux Kernel style):

```ShellSession
betty-style file1 [file2 [file3 [...]]]
```

```ShellSession
betty-doc file1 [file2 [file3 [...]]]
```

#More Info
Betty linter
To run the Betty linter just with command betty <filename>:

Go to the Betty repository
Clone the repo to your local machine
cd into the Betty directory
Install the linter with sudo ./install.sh
emacs or vi a new file called betty, and copy the script below:


#!/bin/bash
# Simply a wrapper script to keep you from having to use betty-style
# and betty-doc separately on every item.
# Originally by Tim Britton (@wintermanc3r), multiargument added by
# Larry Madeo (@hillmonkey)

BIN_PATH="/usr/local/bin"
BETTY_STYLE="betty-style"
BETTY_DOC="betty-doc"

if [ "$#" = "0" ]; then
    echo "No arguments passed."
    exit 1
fi

for argument in "$@" ; do
    echo -e "\n========== $argument =========="
    ${BIN_PATH}/${BETTY_STYLE} "$argument"
    ${BIN_PATH}/${BETTY_DOC} "$argument"
done


Once saved, exit file and change permissions to apply to all users with chmod a+x betty
Move the betty file into /bin/ directory or somewhere else in your $PATH with sudo mv betty /bin/
You can now type betty <filename> to run the Betty linter!
