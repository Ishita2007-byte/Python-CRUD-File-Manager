# Python-CRUD-File-Manager
A Python command-line File Management System that lets users create, read, update, and delete text files. Built using pathlib, os, and exception handling to demonstrate Python file operations and menu-driven programming.
print("press 1 if you want to create file")
print("press 2 if you want to read file")
print("press 3 if you want to update file")
print("press 4 if you want to delete file")
try:
  n=int(input("enter your choice"))
  if(n==1):
    createfile()
  elif(n==2):
    readfile()
  elif n==3:
    updatefile()
  elif n==4:
    deletefile()
  else:
    print("error invalid choice")
except Exception as err:
  print("an exception has occured as:",err)                                                                from pathlib import Path
import os
def createfile():
  try:
    name=input("please enter name of the file you want to create: ")
    path=Path(name)
    if not path.exists():
      with open(path,'w') as f:
        data=input("what do you want to write in your file: ")
        f.write(data)
        print("file sussecfully created")
    else:
      print("ERROR: a file of this name already exists")
  except Exception as err:
    print("an exception has occured as: ",err)                                                                                                               
def readfile():
  try:
    name=input("please enter name of the file you want to read: ")
    path=Path(name)
    if path.exists():
      with open(path,'r') as f:
        READ=f.read()
        print(READ)
    else:
      print("error: file does not exist")
  except Exception as err:
    print("an exception has occured as: ",err)                                                            def updatefile():
  try:
    name=input("please enter name of the file you want to update: ")
    path=Path(name)
    if path.exists():
      update=input("enter whatever you want to add: ")
      with open(path,'a') as f:

        f.write(update + "\n")
    else:
      print("error: file does not exist")
  except Exception as err:
    print("an exception has occured as: ",err)                                                             def deletefile():
  try:
    name=input("please enter name of the file you want to delete: ")
    path=Path(name)
    if path.exists():
      os.remove(path)
      print("file sussecfully deleted")
    else:
      print("error: file does not exist")
  except Exception as err:
    print("an exception has occured as: ",err)                                                                                                     
