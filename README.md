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

# Active-DirectoryPython program that finds the IP address of the domain controller in an active directory:

```
import socket

# Set the domain name of the active directory
domain_name = "mydomain.local"

# Get the IP address of the domain controller
ip_address = socket.gethostbyname(domain_name)

# Print the IP address of the domain controller
print(f"IP address of the domain controller: {ip_address}")

```
This code uses the socket module in Python to find the IP address of the domain controller in an active directory. The socket.gethostbyname() function is used to get the IP address of the domain controller based on its domain name.

To run this code, you can save it to a file and run it using the python command:

```
$ python domain_controller_ip.py
```

This will print the IP address of the domain controller in the active directory. Note that you will need to provide the correct domain name of the active directory in the domain_name variable for this code to work correctly. Additionally, this code may not work if the domain controller is not reachable from the network you are running this code on.






# Active-Directory -  list all username and ip of the internal network domain in the active directory




Here is a simple example of how to write a Python program that lists all the user names and IP addresses of the internal network domain in an active directory:

```import ldap

# Set the domain name of the active directory
domain_name = "mydomain.local"

# Set the LDAP server URL and port
server_url = f"ldap://{domain_name}:389"

# Connect to the LDAP server
server = ldap.initialize(server_url)

# Bind to the LDAP server using the domain administrator credentials
server.simple_bind_s("Administrator", "password")

# Set the search base and filter to get all users in the domain
base_dn = f"dc={domain_name}"
search_filter = "(objectClass=user)"

# Search for all users in the domain
results = server.search_s(base_dn, ldap.SCOPE_SUBTREE, search_filter)

# Print the user names and IP addresses of all users in the domain
print("User names and IP addresses:")
for dn, entry in results:
  # Get the user name and IP address from the LDAP entry
  user_name = entry["sAMAccountName"][0].decode("utf-8")
  ip_address = entry["ipHostNumber"][0].decode("utf-8")

  # Print the user name and IP address
  print(f"{user_name}: {ip_address}")

# Unbind from the LDAP server and close the connection
server.unbind_s()
```
This code uses the ldap module in Python to connect to the active directory and search for all users in the domain. It then prints the user names and IP addresses of all users in the domain.

To run this code, you will need to install the ldap module using pip:

```$ pip install ldap```
Then, you can save the code to a file and run it using the python command:

```$ python user_list.py```
This will print the user names and IP addresses of all users in the active directory. Note that you will need to provide the correct domain name and administrator credentials in the domain_name, server_url, and server.simple_bind_s() function call for this code to work correctly. Additionally, this code may not work if the domain controller is not reachable from the network you are running this code on.
