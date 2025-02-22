# Betty

[![Build Status](https://travis-ci.org/holbertonschool/Betty.svg?branch=master)](https://travis-ci.org/holbertonschool/Betty)

## Installation

Run the script `install.sh` with **sudo privileges** to install `betty-style` and `betty-doc` on your computer. The following manuals will also be installed:

- `betty(1)`
- `betty-style(1)`
- `betty-doc(1)`

## Documentation

For the full specifications of Betty coding and documentation styles, please visit the [Betty Wiki](https://github.com/holbertonschool/Betty/wiki).

You'll also find references and tools for common text editors such as Emacs and Atom.

## Usage

To check if your code or documentation follows the Betty style (which is mostly inspired by the Linux Kernel style), run the following commands:

```sh
betty-style file1 [file2 ...]
```

```sh
betty-doc file1 [file2 ...]
```

## More Info

### Running the Betty Linter

To run the Betty linter using a simple `betty <filename>` command:

1. Clone the Betty macOS fix repository:
   ```sh
   https://github.com/ropkelvin/Betty-macOS-Fix.git
   ```

2. Navigate to the Betty directory:
   ```sh
   cd Betty-macOS-Fix
   ```

3. Install the linter:
   ```sh
   sudo ./install.sh
   ```

4. Create a new script file named `betty` and copy the following script into it:

   ```sh
   #!/bin/bash
   # Wrapper script to run betty-style and betty-doc on multiple files.
   # Originally by Tim Britton (@wintermanc3r), multi-argument support by
   # Larry Madeo (@hillmonkey)

   BIN_PATH="/usr/local/bin"
   BETTY_STYLE="betty-style"
   BETTY_DOC="betty-doc"

   if [ "$#" = "0" ]; then
       echo "No arguments passed."
       exit 1
   fi

   for argument in "$@"; do
       echo -e "\n========== $argument =========="
       ${BIN_PATH}/${BETTY_STYLE} "$argument"
       ${BIN_PATH}/${BETTY_DOC} "$argument"
   done
   ```

5. Save and exit the file.
6. Make the script executable:
   ```sh
   chmod a+x betty
   ```
7. Move the script to a directory in your `$PATH`:
   ```sh
   sudo mv betty /usr/local/bin/
   ```

Now, you can simply run:

```sh
betty <filename>
```

to check your code using the Betty linter!
