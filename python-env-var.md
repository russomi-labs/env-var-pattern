# Using Environment Variables in Python

- Environment variables are inherently not linked with the code
- Best to use in cases where having the variable change with the environment is necessary
- Common use cases are authentication keys, execution mode (e.g. development, staging, production)

## How to Print all Environment Variables

``` Python
import os
print(os.environ)

```

## How to Get Environment Variables

``` Python
os.environ.get('USER')
>>> 'Alice'
```

If there is not a variable matching the key, it will return `None` :

``` Python
os.environ.get('Nonexistent-variable')
>>> None
```

## How to Set Environment Variables

``` Python
os.environ['USER'] = 'Bob'
```

## How to Clear Environment Variables

``` Python
# Clear a single variable
os.environ.pop('USER')

# Clear all variables
os.environ.clear()

```

**Note**
It is important to remember that the settings you apply in a Python script don't
work outside that specific process; `os.environ` doesn't overwrite the environment
variables system-wide. If you need to permanently delete or set environment
variables you will need to do so with a shell environment, such as `Bash` .

## How to Use `dotenv` Manage Environment Variables

dotenv reads in environment variables from a file named .env. The file should be formatted as follows:

``` BASH
api-token = "abcdef_123456"
```

When placed in the same folder as your Python file,
environment variables can be called like so:

``` Python
From dotenv import load_dotenv
load_dotenv()

import os
token = os.environ.get("api-token")
```

## Practical Uses for Environment Variables

### Example of getting the HOME path

``` Python
homepath = os.environ.get(“HOME”)
```


