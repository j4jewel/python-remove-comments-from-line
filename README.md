# python-remove-comments-from-line
Python Code snippet to remove "#" from the beginning of a line.

---
Opening the files using File handler. 
Source file sample.txt
---
cat sample.txt
```sh
Python is a general-purpose programming language that can be used on any modern computer operating system.
#It can be used for processing text, numbers, images, scientific data and just about anything else you might save on a computer.
#It is used daily in the operations of the Google search engine, the video-sharing website YouTube, NASA and the New York Stock Exchange.
These are but a few of the places where Python plays important roles in the success of the business, government, and non-profit
organizations; there are many others.

Python is an interpreted language. This means that it is not converted to computer-readable code before the program is run but at runtimeIn the past, this type of language was called a scripting language, intimating its use was for trivial tasks.
However, programming languages such as Python have forced a change in that nomenclature. Increasingly, large applications are written
almost exclusively in Python.
```
Here the second and third line is commented one. 

The below code will read the file sample.txt and write the uncommented line to result.txt
```sh
with open("sample.txt" , "r") as fh_src:
    with open("result.txt", "w") as fh_dst:
        
        for line in fh_src:
            
            if not line.startswith("#"):
                
                fh_dst.write(line)
```
The output os result.txt
cat result.txt

```sh
Python is a general-purpose programming language that can be used on any modern computer operating system.
These are but a few of the places where Python plays important roles in the success of the business, government, and non-profit
organizations; there are many others.

Python is an interpreted language. This means that it is not converted to computer-readable code before the program is run but at runtimeIn the past, this type of language was called a scripting language, intimating its use was for trivial tasks.
However, programming languages such as Python have forced a change in that nomenclature. Increasingly, large applications are written
almost exclusively in Python.
```

To remove the # and write it to a new file, use the below code

```sh
with open("sample.txt" , "r") as fh_src:
    with open("result.txt", "w") as fh_dst:
        
        for line in fh_src:
            
            fh_dst.write(line.lstrip("#"))
```
The output will be
cat result.txt
```sh
Python is a general-purpose programming language that can be used on any modern computer operating system.
It can be used for processing text, numbers, images, scientific data and just about anything else you might save on a computer.
It is used daily in the operations of the Google search engine, the video-sharing website YouTube, NASA and the New York Stock Exchange.
These are but a few of the places where Python plays important roles in the success of the business, government, and non-profit
organizations; there are many others.

Python is an interpreted language. This means that it is not converted to computer-readable code before the program is run but at runtimeIn the past, this type of language was called a scripting language, intimating its use was for trivial tasks.
However, programming languages such as Python have forced a change in that nomenclature. Increasingly, large applications are written
almost exclusively in Python.

```







