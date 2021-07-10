# python
# this is the code that doesn't preserve the new lines when taking input from one file and writing to the output file.
"""
File: decrypt.py
Project 4.3

Decrypts a text file.  The inputs are the names of
the input file and the output file and the distance value.
The decrypted code is written to a new file.
"""

fileToDecrypt = input("Enter the file to decrypt: ")
distance = int(input("Enter the distance value: "))
outputFile = input("Enter the output file name: ")
text = ""
inputF = open(fileToDecrypt, 'r')
outputF = open(outputFile, 'w' )
lines = inputF.readlines()
for line in lines:
    line = line.strip()
    for ch in line:
        ordvalue = ord(ch)
        cipherValue = ordvalue - distance
        if cipherValue < ord(' '):
            cipherValue = ord('~') - distance - (ord(' ') - ordvalue - 1)
        text += chr(cipherValue)
outputF.write(text)
outputF.close()

