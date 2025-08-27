import os
import shutil


path = input("Enter Location:" )

files = os.listdir(path)

for file in files:
   
    filename, extension = os.path.splitext(file)
   
    extension = extension[1:]
    
    
    if extension == "":
        continue

    if os.path.exists(os.path.join(path, extension)):
      
        shutil.move(os.path.join(path, file), os.path.join(path, extension, file))
    else:
       
        os.mkdir(os.path.join(path, extension))
       
        shutil.move(os.path.join(path, file), os.path.join(path, extension, file))
