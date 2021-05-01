# dotfiles

Create a .dotfiles folder, which we'll use to track your dotfiles.

```git init --bare $HOME/.dotfiles```


Create an alias dotfiles so don't need to type it all over again.

```alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'```

Set git status to hide untracked files

```dotfiles config --local status.showUntrackedFiles no```

Add the alias to .bashrc (or .zshrc) so you can use it later
```echo "alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'" >> $HOME/.zshrc```

### Usage
Use regular git commands such as:

```
dotfiles status
dotfiles add .vimrc
dotfiles commit -m "Add vimrc"
dotfiles add .bashrc
dotfiles commit -m "Add bashrc"
dotfiles push
```


### Setup environment in a new computer

Clone github repository

```git clone --bare https://github.com/USERNAME/dotfiles.git $HOME/.dotfiles```

Define the alias in the current shell scope

```alias dotfiles='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'```

Checkout the actual content from the git repository to your $HOME

```dotfiles checkout```
