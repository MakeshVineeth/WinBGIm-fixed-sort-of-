# WinBGIm

Forked from https://github.com/Duthomhas/WinBGIm-fixed-sort-of-

## How to Download and Compile

Click the little “Download as Zip” button in the upper-right corner here on 
Github and unzip it somewhere convenient.

Then open up your command-prompt in the unzipped directory. The easiest way 
to do this is to double-click on the address bar in Windows Explorer, type 
“`cmd`”, and press `Enter`.

  ![Entering “cmd” into Explorer Address Bar](images/howto-open-cmd.gif)

Once you are at the command prompt, make sure that MinGW is in the path. (If 
you installed it using the default MinGW installation, it should be.) Enter:

    g++ --version
   
This will make MinGW to tell you it is there. If it isn’t 
(`'g++' is not recognized as an internal or external command`), add it with 
_one_ of the following commands, depending on which version of MinGW you have 
installed:

    path C:\MinGW\bin;%PATH%            ←(for MinGW)
    path C:\MinGW-w64\bin;%PATH%        ←(for MinGW-w64)
    path C:\TDM-GCC-64\bin;%PATH%       ←(for TDM-GCC)

Now you are ready to compile WinBGIm and the examples. Enter:

    mingw32-make

and watch it build. You’ll also get to see the two example programs run.

## Compiling your own programs

Once the last step is complete, you now have the following files in the
directory:

    g++bgi.bat
    graphics.h
    libbgi.a

These are the only files you have to care about. Copy them to the same
directory as your program’s source code. Open the command prompt the
same way as before and make sure that MinGW is in the path. If your program’s
source code is named “`myprogram.cpp`”, compile it with:

    g++bgi myprogram.cpp

If you have multiple files that need compiling, list them too:

    g++bgi myprogram.cpp mymenu.cpp myconfigfile.cpp

Assuming you’ve made no mistakes and it compiled, you can invoke your 
executable with:

    myprogram

That’s it!
