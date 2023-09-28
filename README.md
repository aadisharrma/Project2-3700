Project 2: FTP Client

Description:
This project involves the development of an FTP client for interacting with a File Transfer Protocol (FTP) server. A FTP server has been set up for testing purposes at ftp://ftp.3700.network.

Approach:
In this project, several functions were implemented to handle different aspects of FTP communication. The key functions include various send and receive functions, the login function, and command functions.

Explanation of Key Functions:
1. **Connection**: The client connects to the specified host and port by parsing the URL using the `parse_url` function.

2. **Login**: The `login` function reads user-supplied arguments using the `read_args` function, extracts elements from the provided URL, and establishes the FTP login session.

3. **Operation Selection**: An `if` statement determines the operation specified in the command line. For operations that do not involve data transfer, the specified command is passed with the path from the URL. For data transfer operations, a new socket is opened in "Passive Mode," and necessary modes are set with the `set_modes` function.

4. **Data Transfer**: The command is sent to the control socket, and data is received through the data channel socket. Functions like `makeDirectory`, `removeDirectory`, and `delFile` create, delete directories, or remove files in the specified paths.

5. **File Transfer**: The most complex functions are `copyFileFromLocal` and `copyFileFromServer`. They initiate file transfer, either sending a local file to the server or receiving a file from the server, managing data channels.

6. **Closing**: The server connection and control socket are closed using the 'QUIT' command.

Challenges and Difficulties:
Working with sockets and bytes presented challenges initially. Handling data channels for data transfer and processing data as bytes required careful attention. However, with persistence and understanding, these challenges were overcome.

Testing and Debugging:
Testing primarily took place locally, with rigorous debugging to address any issues. Occasional testing on Gradescope helped in refining the code. Exploring other FTP clients could have been insightful, but local testing sufficed for this project.
