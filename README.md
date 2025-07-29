# file-exception-handling
# file handling,exception handling
   Absolute path and relative path

# files
   1.ascii file  
   2.binary file
# paths
# opening a file
# closing a file
# reading a file
# writing a file
# appending a file
# with statement
# without statement


# opening a file 
userdefines=open(filename,mode of the file)
** types of modes **
--> r :- reading the data of the file
--> w :- writting in the file
      if the recomended file is already exist it will write the data in that file if there is no file it will create the file with recomended name
--> a :- append
      the write will clear the previous data from the file and add new data but the append will add the data to the existing file


# reading the data of the file
--> create a folder and store some data in file and than write a code to fetch the data of the file to the present file

file=open('teju.txt', 'r')
data= file.read()
print("file data in teju.txt: ",data)
file.close()

# writing the data in file when the file exists
f=open('write.txt','w')
f.write("Tejaswini...")
f.close()

# writing the data in file when the file not exists
f=open('smile.txt','w') #### give the file name which is not existed then it will create the file with that name and writes the data in it #####
f.write("Tejaswini...")
f.close()
--> output = Tejaswini

# append the data in file
f=open('smile.txt','a')
f.write(" how are you") it will append the data into the file 
f.close()
--> output = Tejaswini how are you

# with statement
*** with open('file.txt','w') as f: ***
with open('smile.txt','w') as f:  ----> we can also use not existed file in file name
    f.write("Hello Teju... How are you")




# EXTENSIONS
--> r+ --> File should exist /overwrites existing content
--> w+ -->Content clarity(refreshes the file)
--> a+ --> Creates a file if not exists, reading woks only after seek()  # [seak() = input from scrach]
                                                                         # [truncate() = the requires data will be taken and unwanted data is removed]



# pgrm
filename='root.txt'
with open(filename,'w') as f:
    f.write("my full name is tejaswini.\n")
with open(filename, 'r+') as file:
    print("latest data:")
    print(file.read())
    file.seek(0)
    userinput=input("\n enter text to overwrite from begining...")
    file.write(userinput)
    file.seek(0)
    print("\n file after writting by r+")
    print(file.read())

# pgrm
with open('line.txt','a+') as file:
    text=input("enter a line to append")
    file.write(text+'\n')
    file.seek(0)
    print("\n current content in the file")
    print(file.read())
# pgrm
'''Write a code that accepts filename as input from the user open the file and count the number if characters appear in the file
   input:s
   output:4
   filedata:mississippi'''
# pgrm
filename=input("enter filename with extensions")
with open(filename,'r') as file:
    text=file.read()
    letter=input("enter a char to search frequency:")
    count=0
    for char in text:
        if char==letter:
            count +=1
print(letter,"appears",count,"times in the file")
