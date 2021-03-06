# Reading and Writing Files

## What Is a File?
### At its core, a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.

### Files on most modern file systems are composed of three main parts:

- **Header:** metadata about the contents of the file (file name, size, type, and so on)
- **Data:** contents of the file as written by the creator or editor
- **End of file (EOF):** special character that indicates the end of the file

## Opening and Closing a File in Python
### When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file.

### When you’re manipulating a file, there are two ways that you can use to ensure that a file is closed properly, even when encountering an error:
1- try-finally block:
```python
reader = open('dog_breeds.txt')
try:
    # Further file processing goes here
finally:
    reader.close()
```

2- with statement:An alternative way of doing this is using with statements. This creates a temporary variable (often called f), which is only accessible in the indented block of the with statement.
```python
with open("filename.txt") as f:
   print(f.read())
```

### You can specify the mode used to open a file by applying a second argument to the open function.

- Sending "r" means open in read mode, which is the default.
- Sending "w" means write mode, for rewriting the contents of a file.
- Sending "a" means append mode, for adding new content to the end of the file.

- Adding "b" to a mode opens it in binary mode, which is used for non-text files (such as image and sound files).

## Reading and Writing Opened Files

### There are multiple methods that can be called on a file object to help you out:

- .read(size=-1): This reads from the file based on the number of size bytes. If no argument is passed or None or -1 is passed, then the entire file is read.

- .readline(size=-1): This reads at most size number of characters from the line. This continues to the end of the line and then wraps back around. If no argument is passed or None or -1 is passed, then the entire line (or rest of the line) is read.

- .readlines(): This reads the remaining lines from the file object and returns them as a list.

## As with reading files, file objects have multiple methods that are useful for writing to a file:

- .write(string): This writes the string to the file.
- .writelines(seq):This writes the sequence to the file. No line endings are appended to each sequence item. It’s up to you to add the appropriate line ending(s).