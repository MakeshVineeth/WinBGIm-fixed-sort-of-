# WinBGIm

Forked from https://github.com/Duthomhas/WinBGIm-fixed-sort-of-
 - Contains additional fixes and vscode config files.
 - Instructions for Dev C++ Setup.
 - Works only on Windows OS.
 - Visit this [Link](https://github.com/Duthomhas/WinBGIm-fixed-sort-of-/tree/master/source) to see what's different from the original WinBGIm library.
 - For Linux or MacOS systems, try this: http://libxbgi.sourceforge.net (not tested)

# Introduction

In this repo, you'll find the instructions to compile graphics.h from source code and use it on your Windows Systems with Dev C++ and Visual Studio Code. graphics.h provides access to Simple Graphics Library which can be used to put pixels, draw lines and circles etc using C/C++

**NOTE: graphics.h has been discontinued 20+ years ago, it is recommended to switch to any newer graphics libraries like SDL, OpenGL etc.**

## How to Download and Compile

Click the little “Download as Zip” button in the upper-right corner here on 
Github and unzip it somewhere convenient.

Then open up your command-prompt in the unzipped directory. The easiest way 
to do this is to double-click on the address bar in Windows Explorer, type 
"`cmd`", and press `Enter`.

  ![Entering "cmd" into Explorer Address Bar](images/howto-open-cmd.gif)

Once you are at the command prompt, make sure that MinGW is in the path. (If 
you installed it using the default MinGW installation, it should be.) Enter:

    g++ --version
   
This will make MinGW to tell you it is there. If it isn’t 
(`'g++' is not recognized as an internal or external command`), add it with 
_one_ of the following commands, depending on which version of MinGW you have 
installed:

    path C:\MinGW\bin;%PATH%            ← for MinGW
    path C:\MinGW-w64\bin;%PATH%        ← for MinGW-w64
    path C:\TDM-GCC-64\bin;%PATH%       ← for TDM-GCC

Now you are ready to compile WinBGIm and the examples. Enter:

    mingw32-make

and watch it build. You’ll also get to see the two example programs run.

## Compiling your own programs

Once the last step is complete, you now have the following files in the
directory:

    g++bgi.bat
    graphics.h
    libbgi.a

These are the only files you have to care about. There are two ways to compile:

### Method 1
Copy them to compiler's directories so that it is globally accessible to all source code files. Following are the steps:

- Copy graphics.h file to the **include** directory of the compiler.
- Copy libbgi.a file to the **lib** directory of the compiler.
- Copy **g++bgi.bat** to bin folder.

### Method 2
Copy them to the same
directory as your program's source code. Open the command prompt the
same way as before and make sure that MinGW is in the path. If your program's
source code is named "`myprogram.cpp`", compile it with:

    g++bgi myprogram.cpp

If you have multiple files that need compiling, list them too:

    g++bgi myprogram.cpp mymenu.cpp myconfigfile.cpp

Assuming you’ve made no mistakes and it compiled, you can invoke your 
executable with:

    myprogram


## VS Code Setup

- Create a Workspace folder, make sure there are no spaces or special characters in the path, else it may not work properly.
- Copy the .vscode folder inside that Workspace folder.
- Now open the folder in VSCode and write any graphics program.
- Make sure to save it as **.cpp**, else it will not work.
- Now press Ctrl + Shift + B to build and run your program.

## Dev C++

- Use a recent version of Dev C++ (https://www.embarcadero.com/free-tools/dev-cpp)
- Open the Dev C++ application.
- Choose only 32-bit compiler from the drop down menu as graphics.h doesn't work with 64bit versions.
- Go to Compiler options from the menu.
- Paste the following lines in the Linker options: `-lbgi -lgdi32 -lcomdlg32 -luuid -loleaut32 -lole32`
- Write any graphics program and make sure to save it as **.cpp**
- Run your program!


HAPPY CODING !
