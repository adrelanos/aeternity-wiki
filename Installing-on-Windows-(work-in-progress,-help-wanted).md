It is not confirmed whether we want to go that route: https://github.com/aeternity/testnet/issues/5

I thought that if the code is written in Erlang, it should be possible to run on any platform.

In my work as web developer I make web apps look sleek and load fast, I hate managing dependencies and solving build issues. But I gave it a shot anyway, it cannot be that hard?

----

These instructions assume basic familiarity with command line. The fastest way to launch it is `WIN + r` and then type `cmd`... You can navigate the folders using some basic commands such as

* `cd c:/` _(go to a drive)_ 
* `cd ..` _(to go level up)_ 
* `cd FOLDER_NAME` _(go deeper)_ 
* `dir` _(list contents)_

These are the very basic commands so that you know how to navigate folders from command line. I suggest creating a folder `c:/code` to keep all your code there. The command `md code` creates the folder.

## 0. Download and install Git

https://www.google.com/search?q=install+git

In that way you'll be able to get the source code directly from repository.

## 1. Download and install Erlang

https://www.erlang.org/downloads

For the more adventurous, build it from source.

## 2. Add the folder to the path

**On Windows 10:** Right click on the start button - System - _(left hand side)_ Advanced system settings - Environment Variables - find `path` - Edit... - New - on my machine it is `c:\Program Files\erl8.3\bin`

It many clicks away, I've reported a usability bug, it's by design: http://imgur.com/a/qbeTc


## 3. Install rebar

A very detailed set of instructions can be found on this link: http://theburningmonk.com/2014/08/getting-started-with-rebar-on-windows/

In case the link goes offline:

**3.1)** `git clone https://github.com/rebar/rebar`

**3.2)** go into that directory and run `bootstrap.bat`

**3.3)** same business as previously, add the directory to the path so that you can execute `rebar`


## 4. Get code and dependencies:

**4.1)** `git clone https://github.com/aeternity/testnet.git`

**4.2)** `rebar get`

**4.3)** `rebar compile`

It is likely that it will throw an error:

```
Compiling c:/code/testnet/deps/jiffy/c_src/decoder.c
'cl.exe' is not recognized as an internal or external command,
operable program or batch file.
ERROR: compile failed while processing c:/code/testnet/deps/jiffy: rebar_abort
```

## 5. Get C++ compiler

**5a)** You can get a standalone version: https://visualstudio.uservoice.com/forums/121579-visual-studio-ide/suggestions/6742251-make-c-c-compiler-cl-exe-independent-of-ide

As you can see it was a popular request and they delivered, good for Microsoft!

**5b)** If you have Visual Studio already installed - most probably you have default version _(without C++ compiler)_

Go to Control Panel - Programs - Visual Studio - modify... It will launch the installer and it will allow you to select `C++` 

_(or `Visual C++`, I don't know the difference but `Visual C++` was the closest to `C++` I could find)_

## Help needed!

That's where it goes bad: https://github.com/davisp/jiffy/issues/144

> Any idea where assert.h lives on Windows?

> It should be part of the std library