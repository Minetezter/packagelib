# packagelib

Create and publish your modules to PyPI all in python!

# Importing packagelib:

**How to import packagelib with no issues:**

```python
import packagelib.main
```

# Naming your module:

Give your module a name using the packagelib.name() function:

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
```

# Setup files and directories:

Setup all files and directories with the packagelib.setup() function:

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()
```

# Give your package a PyPI description:

This will be the description that shows up on PyPI:

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
```

# Upload a script to your module:

This will be the script that will contain your code. Make sure you have the right content.

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("myCode.py") # Enter a file name with your code
```

**OR**

Enter the script directly:

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("""
    def add_one(number):
        return number + 1
""")
```

**ALSO**

You can write the \_\_init\_\_.py file:

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("myCode.py", init="import requests")
```

**AND**

Your module will automatically be a package. For example, my module I am using as an example (MyExamplePackage) would be imported as 'MyExamplePackage.main'.
You can change the name of the package from 'main', by changing the optional argument [name] to your choice.
You can also allow you module to not be imported as a package by adding the text 'import main' to the \_\_init\_\_.py file.

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("myCode.py", name="code")
```

The example above would make the module "MyExamplePackage" be imported as "MyExamplePackage.code"

# Giving you module a license:

Currently, this version only allows MIT and AGPLv3, but more should be coming

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("myCode.py")
pack.license().mit() # if you would like an AGPLv3 license, just replace 'mit()' with 'agplv3()'
```

# Adding required data to your module

Use the packaglib.noteInfo(version, author, email, python-version, description) function to add required info to your module.
In the 'version' argument, put the version of your module
In the 'author' argument, please put your name or username
In the 'email' argument, put the email address associated with your module.

If you have posted your code on GitHub, also fill out the 2 arguments 'homepage' and 'bugs':
The 'homepage' argument is the homepage of your module on GitHub.
The 'bugs' argument is the bug tracker associated with your module on GitHub.

**Example:**

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("myCode.py") 
pack.license().mit()
pack.noteInfo(
  '0.0.1',
  'My Name',
  'MyEmail@example.net',
  '3.7',
  'This is a test package!!!'
  home='https://github.com/MyUsername/MyExamplePackage'
  bugs='https://github.com/MyUsername/MyExamplePackage/issues'
)
```

# Compile your module:

Compile your module files into a complex binary format to be published:

```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("myCode.py") 
pack.license().mit()
pack.noteInfo(
  '0.0.1',
  'My Name',
  'MyEmail@example.net',
  '3.7',
  'This is a test package!!!'
  home='https://github.com/MyUsername/MyExamplePackage'
  bugs='https://github.com/MyUsername/MyExamplePackage/issues'
)

pack.buildDist()
```

# Finally, publish your module:

When you run this command, keep in mind it will also put it on TestPyPI by default, so you must set the optional argument 'test' to False.
```python
import packagelib.main as pack

pack.name("MyExamplePackage")
pack.setup()

pack.description("This is my example package with packagelib!!")
pack.uploadScript("myCode.py") 
pack.license().mit()
pack.noteInfo(
  '0.0.1',
  'My Name',
  'MyEmail@example.net',
  '3.7',
  'This is a test package!!!'
  home='https://github.com/MyUsername/MyExamplePackage'
  bugs='https://github.com/MyUsername/MyExamplePackage/issues'
)

pack.buildDist()

pack.publish('MyUsername', test=False)
```

# I hope you enjoyed creating your module!
# Thanks!

Please visit my GitHub account [here](https://github.com/Minetezter)!
