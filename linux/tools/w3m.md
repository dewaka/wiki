# W3M command line browser 

- w3m can display images in a terminal, provided the terminal has necessary
  capabilities, but if you want to browse just text only, then use,
  `auto_image=FALSE` option as follows,
  
  ```sh
  w3m -o auto_image=FALSE  https://news.ycombinator.com/
  ```
