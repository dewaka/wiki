# tmux 

## Links

- [Scripting tmux](https://www.arp242.net/tmux.html)

## Current config

- [tmux.conf](https://gist.github.com/dewaka/ec7c77eb47488028e5e2b8260f0d38a3)

## Color scheme

- [gruvbox theme](https://github.com/dewaka/tmux-gruvbox) - I forked the
  repository to add Zoom indicator icon support.

## Tmux Cookboook

- Rename tmux windows to current directory - <https://stackoverflow.com/questions/28376611/how-to-automatically-rename-tmux-windows-to-the-current-directory>

  ```tmux
  set-option -g status-interval 5
  set-option -g automatic-rename on
  set-option -g automatic-rename-format '#{b:pane_current_path}'
  ```
- Manually rename windows with - `Prefix + ,`
- To show current bindings - `Prefix + ?`
