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
