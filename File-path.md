# File Path:

**1. Absolute File Path**
**2. Relative File Path**


## Absolute File Path:
The root is `/`. <br>

Absolute file paths always start off relative to the `root`. It basically just starts from the origin (the root of the computer).

Example: <br>
`/work/report.doc`

## Relative File Path
Relative file path looks in the current folder for the file. <br>

`.` (single dot): current directory you are in.

`..` (double dot): parent directory (the folder right above the current one).


For example:<br>

*Absolute file paths*:
`/work/project/main.py`

1. If your current directory is `/work/project/`, your relative path would be:
   `./main.py`

2. If your current directory is `/work/`, your relative path would be:
   `./project/main.py`

**Note:**<br>
We can write the relative path without `./`, like `project/main.py`


---------------

# Jumping back to the previous/parent directory :

For each jump you need to use `../` <br>

For example if you are in :
* **Windows** : `F:\python\new-folder`
* **Unix/Linux/macOS** : `/F/python/new-folder` (if 'F' were a folder name) <br>

And your `text.txt` file is in the `F` directory : <br>
`../../test.txt"`


-----------------------------
