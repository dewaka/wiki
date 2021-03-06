# Vim

I'm a big fan of modal editing and specifically Vim.

## Resources

### Videos

- [Derek Wyatt Vim Videos](http://derekwyatt.org/vim/tutorials/) - The first
  time I came across their videos was on global commands - [Globals, Command Line and Functions](https://vimeo.com/15443936). 
  This is a pretty good video to show some _magic_ of Vim and it is very funny to boot! This would be my
  current video of choice to show someone the power of Vim at the hands of an advanced user.
- [Greg Hurrell](https://www.youtube.com/channel/UCXPHFM88IlFn68OmLwtPmZA) - Greg's channel is not exclusively about Vim, 
  but his channel full of Vim tips and tricks.

## Tips

- Map `CapsLock` to `Esc`
	-	In Linux I've used [xmodmap](https://www.x.org/archive/X11R6.8.1/doc/xmodmap.1.html) based method
	  for mapping for this.
	
		```conf
		! Swap caps lock and escape
		remove Lock = Caps_Lock
		! keysym Escape = Caps_Lock
		keysym Caps_Lock = Escape
		add Lock = Caps_Lock

		! Press both Shift keys to get Caps_Lock
		keycode  50 = Shift_L Caps_Lock Shift_L Caps_Lock
		keycode  62 = Shift_R Caps_Lock Shift_R Caps_Lock
		```
	- On macOS this could be done via settings -
	  <https://stackoverflow.com/questions/127591/using-caps-lock-as-esc-in-mac-os-x>.
- Appending result from an external command to the buffer -
  <https://vim.fandom.com/wiki/Append_output_of_an_external_command>
  
  `read !<external command>`
  
  For example, to get CPU info into the current buffer, `read !cat /proc/cpuinfo`.
- Format JSON,
  - with `python` - `:%!python -m json.tool`
  - with `jq` tool - `:%!jq '.'`
- Change `Tabs` to `Spaces` -
  <https://stackoverflow.com/questions/426963/replace-tabs-with-spaces-in-vim>
  
  ```vim
  " settings for tabs
  :set tabstop=2 shiftwidth=2 expandtab
  " convert the existing buffer
  :retab
  ```
  
  Another option to would be to _reindent_ the whole file with `gg=G`.
- Enabling mouse scroll support -
  <https://stackoverflow.com/questions/7225057/use-mouse-scroll-wheel-in-vim>.

  ```
  set mouse=a
  ```
- Opening files based on a command line search. This is more of a command line
  tip, but I find this pattern to be quite useful. To open all Dockerfiles in a
  directory,
  ```
  vim $(fd Dockerfile ~/Code)
  ```
  
  Another adaptation of this pattern is to use a temporary vim buffer to put the
  search results and then open files based from buffer contents.
  ```
  fd Dockerfile ~/Code | vim -
  
  # Then open files one by one based on the contents (which could be empty if
  # the search results are empty). Opening buffers for file locations is a
  # pretty easy in Vim with Vim unimpared commands like `gf` in normal mode
  ```
- Write a file as superuser,
	```vim
  :w !sudo tee %
  ```

	How this works - <https://stackoverflow.com/questions/2600783/how-does-the-vim-write-with-sudo-trick-work>.
- [Vim regex](http://vimregex.com/)
