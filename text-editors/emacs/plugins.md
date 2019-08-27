# Emacs Plugins

## Evil

I find evil mode to be an essential plugin to make use of the Vim muscle memory
I've developed over the years for editing. Another reason is that I find modal
editing to be less straining for extended typing compared to Emacs', notorious
strain on hands due to key combinations. Emacs plugins like
[god-mode](https://github.com/chrisdone/god-mode) can somewhat help with the
key combination situation, Vim modes takes it a couple of notches higher.

## Projectile

This is a pretty useful plugin for working with /projects/. Projects are usually
any source controlled directory, or any directory with a `.projectile` (empty)
file. Projectile allows, among other things, to apply commands in bulk mode
within the current buffer's project. This is best explained via some examples,

- `projectile-kill-buffers` - This command will close all the buffers of the
  current project you are working on.
