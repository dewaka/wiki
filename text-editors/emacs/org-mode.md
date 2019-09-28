# Emacs Org Mode

## Capture Templates

- Capturing in a datetree format,

  ```elisp
  ("i" "Ideas" entry
   (file+olp+datetree (lambda () (concat org-directory "/ideas.org")))
   "** %^{Heading}")
  ```
  
## Creating tables

- To create a table in org-mode, enter columns between `|`, and to get a header
  sepearator just enter `|-` and press `Tab`.
  
  Example from -
  <https://orgmode.org/manual/Built_002din-Table-Editor.html#Built_002din-Table-Editor>.
  
  ```
  | Name | Phone | Age |
  |-
  ```
  is all that's required to get the following table,
  
  ```
  | Name | Phone | Age |
  |------+-------+-----|
  |      |       |     |
  ```

