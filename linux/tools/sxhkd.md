# sxhkd

## Key chording

You can do key chording with sxhkd. For example, following example makes use of
key chording to [jump](jumpapp.md) into apps.

```conf
# App jump chords
super + j; {g,f,t,e,v,p}
	jumpapp -m {googl-chrome,firefox,xfce4-terminal,emacs,gvim,postman}
```
