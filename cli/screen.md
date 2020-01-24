# screen 

One advantage of `screen` is that it is a default package on most Unixy systems.
Thus if you logged into a remote server you are more likely to have `screen`
available for use than `tmux`.

This is why it is worth learning basics of `screen`.

# Splitting 

- Screen window splitting - <https://tomlee.co/2011/10/gnu-screen-splitting/>
- Unlike on `tmux` a shell has to be spawned explicitly after splitting.
- To do a vertical split - `Ctrl+a |` then `Ctrl+TAB` to go to the other
    split. Then as usual, use `Ctrl+a c` to create a window.
- For a horizontal split use `Ctrl+a S`.
