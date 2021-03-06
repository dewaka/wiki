# fish shell

[fish](https://fishshell.com) is a non-POSIX commplient shell which I find to be
really good for day to day use.

## Managing fish plugins

- fisher - plugin manager

## Miscellaneous tips

- Directory variables

  ```fish
  # Useful directories
  set -x Dropbox   $HOME/Dropbox
  set -x Projects  $Dropbox/Projects
  ```
  
  This makes it pretty easy to run commands regardless of the current working
  directory. Example, to search for all files with `__main__` in projects
  directory,
  
  ```fish
  rg '__main__'  $Projects
  ```
- `Alt+Back` - to go back in directory history and `Alt+Right` to forward.
- `Alt+v` - to edit command with shell's default editor. This is looked up via the `$EDITOR` environment variable.
- `Alt+f`, `Alt+b` - to go forward adn backward in currently editing command. These are Emacs readline keys which fish prompt support out of the box.

## Useful functions

- Run in directory

  ```fish
  # Mnemonic - Run in Directory
  function rd --description "run given commands in directory without changing current directory"
  	set dir $argv[1]
  	set --erase argv[1]
  	if test -n "$dir"
  		# Run in a sub shell so that we do not change directory stack
  		fish -c "
  		pushd $dir
  		eval $argv
  		"
  	end
  end
  ```
  
  This is pretty useful to run a command in a different directory from the one
  you are currently working in. For example, I use this frequently to check the
  `git status` of the notes directory with - `rd $Notes git status`, where
  `$Notes` is a directory alias to the Notes directory. Since the subcommands
  run in a fish shell, you can use usual conviniences such a abbreviations and
  aliases. Thus above command can be shortened to, `rd $Notes gs` in my
  configuration.
  
- Create directory and `cd` into it,

  ```fish
  # From - http://unix.stackexchange.com/questions/125385/combined-mkdir-and-cd
  function mkcd --argument-names 'path'
    if test -n "$path"
      mkdir -p -- "$path"; and cd "$path"
    end
  end
  ```

- Find out the ID of the running container for given search term

  ```fish
  function container-id
    set search $argv[1]
    set --erase argv[1]
    if test -n "$search"
      docker ps | grep "$search" | cut -f1 -d' '
    end
  end
  ```
  
  Usage example: To find out currently running Postgres instance - `container-id postgres`.
