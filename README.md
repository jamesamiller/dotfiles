# macOS dotfiles

## Installation

You can clone the repository wherever you want. (I keep it in `~/GitHub/dotfiles`.) A script will then set up symbolic links from the home directory to the local repository.

```bash
git clone https://github.com/jamesamiller/dotfiles.git
```

To set up the symbolic links, `cd` into your local `dotfiles` repository and then

```bash
chmod u+x symlinks.sh
./symlinks.sh
```

## Add custom commands without creating a new fork

If `~/.extra` exists, it will be sourced along with the other files. You can use this to add a few custom commands without the need to fork this entire repository, or to add commands you don’t want to commit to a public repository.

As an example, `~/.extra` could contain

```bash
# Git credentials
# Not in the repository, to prevent people from accidentally committing under my name
GIT_AUTHOR_NAME="Mathias Bynens"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
git config --global user.name "$GIT_AUTHOR_NAME"
GIT_AUTHOR_EMAIL="mathias@mailinator.com"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
git config --global user.email "$GIT_AUTHOR_EMAIL"
```

You could also use `~/.extra` to override settings, functions and aliases from my dotfiles repository. It’s probably better to this repository instead, though.


