# FTP Client

A basic FTP client that implements the FTP protocol and allows the user to perform operations such as ls and mv on an FTP server. The user can provide an FTP URL as an argument to the client to specify which server they want to connect to and what file or directory they want to interact with.

## Requirements

Python3

## Usage

The client can be executed by running the following command in the terminal:
'''
./3700ftp <operation> <parameters>
'''

- <operation> specifies the FTP command to execute, e.g. ls.

- <parameters> is a list of one or more parameters, including an FTP URL that specifies the server and file or directory to interact with. The FTP URL should have the following format:

'''
ftp://[USER[:PASSWORD]@]HOST[:PORT]/PATH
'''

## Functionality
The client implements the following FTP commands:

- `USER`
- `PASS`
- `TYPE`
- `MODE`
- `STRU`
- `PASV`
- `RETR`
- `STOR`
- `DELE`
- `RMD`
- `MKD`
- `PWD`
- `CWD`
- `QUIT`

and supports the following functionality:
- `ls <URL>`                 Print out the directory listing from the FTP server at the given URL
- `mkdir <URL>`              Create a new directory on the FTP server at the given URL
- `rm <URL>`                 Delete the file on the FTP server at the given URL
- `rmdir <URL>`              Delete the directory on the FTP server at the given URL
- `cp <ARG1> <ARG2>`         Copy the file given by ARG1 to the file given by
                             ARG2. If ARG1 is a local file, then ARG2 must be a URL, and vice-versa.
- `mv <ARG1> <ARG2>`         Move the file given by ARG1 to the file given by
                             ARG2. If ARG1 is a local file, then ARG2 must be a URL, and vice-versa.
                             
## Approach
I utilized the suggested implemtation approach: first beginning by parsing arguments using the `argparse` library, and then ensuring I could extract the necessary data from the FTP URL by using the `urllip.parse` library. I implemented the `mkdir`, `rmdir`, and `rm` functions first, before moving on the functionality that required the creation of a data channel. After I established a method to create a data channel, I implemented the `ls` function. I then implememted the `cp` function. Finally, I utilized the `rm`, `cp`, and the `os` library for the `mv` function.

## Challenges
This project was challenging for me as it was one of my first times writing a full program in Python. Learning the language and different libraries as I  worked was a challenge, but it became more fun and rewarding as I found my footing.

## Testing
I tested my code through the command line.
