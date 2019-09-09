# Emacs Org Mode

## Capture Templates

- Capturing in a datetree format,

  ```elisp
  ("i" "Ideas" entry
   (file+olp+datetree (lambda () (concat org-directory "/ideas.org")))
   "** %^{Heading}")
  ```
  
