# Emacs

I tend to use Emacs with _evil-mode_ for any kind of extended editing and
programming, unless I'm using an IDE (with a Vim plugin of course!) in the
latter case.

One of the disadvantages of evil-mode is that there's a high chance that
advanced commands _might_ not as expected in Emacs. For example, `:normal ...`
commands do not work in evil-mode. Also Vim regex and Emacs regex are not
really compatible - so your Vim regex know-how will not translate directly to
Emacs. So, when it comes to raw editing Vim probably is the better editor from
my experience.

However, with evil-mode one can easily use Emacs editing functionality as well
which comes with the downside of haing to learn two disparate kind of editing
paradigmns.

## Configuration distributions

### Spacemacs

This is what I have been using for a couple of years and I would recommend this
someome wanting to transition from Vim to an Emacs workflow.

### [Doom Emacs](doom.md)

I have been trying this configuration package recently and I am quite impressed
with the low startup overhead of the Doom configuration.

### Blogs

- [Xah Emacs Blog](http://ergoemacs.org/emacs/blog.html)
- [Emacs Rocks](http://emacsrocks.com/)
- [Sacha Chua - Emacs](https://sachachua.com/blog/category/emacs/) - Sacha's
  blog has a treasure trove of Emacs knowledge both written by herself and
  aggregated links.

