# sxhkd

## Managing fish plugins

- fisher - plugin manager

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
  
