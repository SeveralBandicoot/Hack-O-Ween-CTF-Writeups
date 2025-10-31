Challenge 2: Linux Terminal Binary Execution 

The goal for this challenge was to analyze the provided executable file, LinkedRooms.exe, to extract the hidden 
flag without needing to execute or reverse-engineer the application fully. 

##Tools Used
- Terminal/Command Line: Used to interface with the file. 
- strings command: Used to extract all printable text sequences from the binary file. 

##Thinking Process

1. Static Analysis Decision: Given the file was an executable (.exe) and the challenge title hinted at a terminal interface, the most effective first step was to perform static analysis to check if the flag was stored in plain text within the binary itself.

2. Executing the strings command: I navigated to the directory containing LinkedRooms.exe and ran the strings command, 
which outputs all human-readable character sequances (strings) found in the file:

strings LinkedRooms.exe

##Flag Extraction: 
I analyzed the extensive output from the command, specifically searching for common CTF patterns like flag, flame, or any other strings related to the challenge theme. 
The string skin_stealer was identified wihin the output, which, when combined with the required flag format, yielded the final answer. 
We were given the folder LinkedRoom, the files contained in this folder were LinkedRooms.exe. The flag for this challenge was "flame{skin_stealer}".
