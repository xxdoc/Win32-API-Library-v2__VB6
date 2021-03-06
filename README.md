# Win32-API-Library-v2__VB6
Software Development: Win32 API Library v2.0<br><br>

<h4>EVENT LOG MESSAGE DLL</h4>

<h5>INTRODUCTION</h5>

This section only applies if you wish to use the EventLog object of the Win32APILibrary. The EventLog object uses a message dll for all the error message and adds these to the event log, this is simply a resource dll containing the MessageID and related message string.


sample.mc - A sample message file
build.bat - Batch file to build the message dll


<h5>USING THE MESSAGE DLL</h5>

Using the sample.mc file create your message file, follow the format of the existing sample file and create a block for each error message that you want to enter into the event log. Ensure that the very last line of the message file is a full stop(.) on its own.

MessageID
........
.
MessageID
.......
.

Once you have written your message file from the start menu select Run and type command followed by Ok, this will open the Dos command window.

At the DOS prompt type the following

CD [PATH_TO_MSGDLL_FOLDER]
build [MESSAGE_FILE] [MESSAGE_DLL]

**PATH_TO_MSGDLL_FOLDER - Enter the path to your message dll folder, for example CD src\win32a~1\msgdll
**MESSAGE_FILE - The name of your message file without the file extension
**MESSAGE_DLL - The name of the message dll output file

Example:

C:>CD src\win32a~1\msgdll
C:SRC\WIN32A~1\MSGDLL>build sample mymsg

The batch file will create a message dll and it will copy the dll to the system32 folder in your windows directory.
Once this process is complete type exit at the command prompt to close the dos window.
You now have a message dll ready to use with the EventLog object in the Win32APILibrary.
