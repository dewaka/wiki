# Requests

- [https://2.python-requests.org/en/master/user/advanced/#session-objects](Session objects) - Creating a 
  session allows setting common headers, such as Authorization headers, for a set of requests,
  
  ```python
  s = requests.Session()
  s.headers.update({'Authorization': 'auth_data'})
  s.get(...) # Will contain Authorization details provided earlier
  ```
