**How to get data from post request body**

```python
# method 1

body = request.get_json()
data = body.get("data_name", None) # getting the data

# method 2 get specific data at once
data = request.get_json()["data_name"]
```

**How to get arguments from a request**

```python
my_arg = request.args.get("arg_name", "default_arg")
e.g
page = request.args.get(page, 1)
```
