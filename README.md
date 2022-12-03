# Active-Directory
Here is a simple example of how to write a Python program that gets information about the current active directory:

```
import os

# Get the current working directory
cwd = os.getcwd()

# Print the current working directory
print(f"Current working directory: {cwd}")

# Get the list of files and directories in the current working directory
contents = os.listdir(cwd)

# Print the list of files and directories in the current working directory
print("Contents of the current working directory:")
for item in contents:
  print(item)
  ```
This code uses the os module in Python to get information about the current active directory. The os.getcwd() function is used to get the current working directory, and the os.listdir() function is used to get the list of files and directories in the current working directory.

To run this code, you can save it to a file and run it using the python command:

```
$ python active_directory.py
```
This will print the current working directory and the list of files and directories in it. You can also provide a different directory as an argument to the os.listdir() function to list the contents of that directory instead of the current working directory. For example:

```
import os

# Get the list of files and directories in the specified directory
contents = os.listdir("/path/to/directory")

# Print the list of files and directories in the specified directory
print("Contents of the specified directory:")
for item in contents:
  print(item)
  ```
This code will list the contents of the /path/to/directory directory instead of the current working directory.
