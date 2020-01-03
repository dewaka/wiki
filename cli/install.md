# install command

This is a very useful command for copying files with extra functionality,

- Change permissions

  ```sh
  install -x644 path/to/source path/to/destination
  ```
  
  Setting permissions to 644 after copying.

- Create directory hierarchies
  
  ```sh
  install -d path/to/source path/to/destination
  ```
  
  Here the destination path's directory hierarchies will be created as needed.


