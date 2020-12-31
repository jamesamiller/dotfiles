# macOS dotfiles

## Installation

Clone this to a local repository. I use `~/GitHub/dotfiles`. 

```bash
git clone https://github.com/jamesamiller/dotfiles.git
```

The script `symlinks.sh` will then set up symbolic links from the home directory to the local repository files. **NB:** Delete any existing `.bash_profile` file before establishing the sym link to the local repo `.bash_profile` file.

 `cd` into your local `dotfiles` repository and then

```bash
chmod u+x symlinks.sh
./symlinks.sh
```

## Unused Files

The files or directories in this repo I currently use are

```bash
.aliases
.bash_profile
.bash_prompt
.bashrc
.exports
.extra
.functions
symlinks.sh
macos.sh
```

## Add custom commands without committing

If `~/.extra` exists, it will be sourced along with the other files. You can use this to add a few custom commands without the need to commit.

As an example, `~/.extra` could contain
```bash
source /opt/intel/bin/compilervars.sh intel64
source /opt/intel/mkl/bin/mklvars.sh intel64 mod
```
if we use an Intel compiler. Or the conda initialize code 
```bash
# >>> conda initialize >>>
# !! Contents within this block are managed by 'conda init' !!
__conda_setup="$('/opt/anaconda3/bin/conda' 'shell.bash' 'hook' 2> /dev/null)"
if [ $? -eq 0 ]; then
    eval "$__conda_setup"
else
    if [ -f "/opt/anaconda3/etc/profile.d/conda.sh" ]; then
        . "/opt/anaconda3/etc/profile.d/conda.sh"
    else
        export PATH="/opt/anaconda3/bin:$PATH"
    fi
fi
unset __conda_setup
# <<< conda initialize <<<
```
that gets added to `.bash_profile` with an Anaconda install.


