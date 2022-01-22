# How-to-Install-JUCE-on-Ubuntu-20.04

## TLDR
There are two ways to get up and running with `JUCE` on `Ubuntu`.

    - Option 1 - The Download Technique
    Simply download, uncompress, then double-click the `Projucer` application which is ready to run with no installation needed.

    https://juce.com/get-juce/download


    - Option 2 - The `apt` Technique
    You can also install the official bits blessed by the `Ubuntu` team by using `apt`, the official package manager.


        #update package list
        sudo apt update

        #install JUCE
        sudo apt install -y juce-tools juce-modules-source


## Intro
In this write-up we discuss getting your `Ubuntu 20.04` system up and running with `JUCE`, the open-source framework for creating audio plugins, dsps, etc.


## Checking your OS Version
You can check your os version with:

    cat /etc/os-release


## Optional - Review dependencies (if any)
When landing at the following link, be sure to select your OS from the top right of the page if you are not on `focal` (`20.04`).

    https://packages.ubuntu.com/focal/juce-tools


## About `Projucer`
The `Projucer` application is the official GUI application for working with the `JUCE` framework. You will get this with either the download or the `apt` technique.


## The `Projucer` application as a "download"
We can download the bits and start creating things immediately without needing to compile or do anything tricky.  Just click the link in the "TLDR" above and you can extract the `.zip` file and locate the `Projucer` application.  The `Projucer` application will already be executable and you can simply launch it, though feel free to review the properties if desired.


## The `Projucer` application from `apt`
Here we just repeat the steps shown in the TLDR since the `apt` technique is that easy.

    #update package list
    sudo apt-get update

    #install JUCE
    sudo apt install -y juce-tools juce-modules-source


*Note: This will also result in a nice GUI experience once we get the bits installed.*


## Launching `Projucer`
After installing with `apt` we will have an icon in our Applications menu.  You want to show off right away and add this as a favorite.


*Note: If you are running `projucer` that you downloaded from the website, then you can navigate manually when wanting to launch `projucer` (i.e. to your `Downloads` or `/home` directory, wherever you placed the bits).*


## Running Both Versions
You can run the latest version which you downloaded manually from the site (in the TLDR) which is currently version `6.1.4` as of this writing.  However, the version that we get from our `Ubuntu` package manager will be version `5.4.7` currently (a little behind as expected).


## Optional - Install VS Code
`Juce` has its own editor / IDE, but you can also install `Visual Studio Code`, if desired.

    #download gpg key
    wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
    
    #add gpg key
    sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
    
    #Copy/Paste the following very long one-liner
    sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

    #cleanup
    rm -f packages.microsoft.gpg

    #refresh package list
    sudo apt update

    #install visual studio code
    sudo apt install code


## Optional - Adding VS Code `extensions`
If using `Visual Studio Code`, be sure to click the `extension` icon in the left pane and search for the `c++` extension from `microsoft`.

You will also want the "extension" pack from `microsoft` which includes additional support for C++ and can be installed like normal.


*Tip: Not needed, but the nerd-mode extension install technique is press `ctrl + p`, to access the vs code `quick open` menu, then paste an `ext` command such as `ext install ms-vscode.cpptools-extension-pack`.*


## Optional - Installing more build tools
`Juce` should have everything you need, but if going all out you might also want `g++` which you can install on its own, or better yet as part of the official Ubuntu package known as `build-essential`.

    #optional
    sudo apt install -y build-essential

## Recommended - `Hello World` examples (compile with vs code)
By doing the official Microsoft "hello world" tutorials for `c++`, you will further get your system ready for working with `JUCE`.

    #supporting links
    https://code.visualstudio.com/docs/languages/cpp
    https://code.visualstudio.com/docs/languages/cpp#_tutorials
    https://code.visualstudio.com/docs/cpp/config-linux

*Note: We can optionally add support for `cmake` as well if desired, but not required.  See https://code.visualstudio.com/docs/cpp/cmake-linux for more detail on setting up support for `cmake` in Visual Studio Code.*


## Summary
In this write-up we got you up and running with `JUCE` on `Ubuntu 20.04`.


## Next Steps
Get started coding with the `JUCE` framework by reviewing the official get started guides which take you from start to finish and have many options if you want to skip ahead directly to a topic that interests you; Or follow the guide straight through!

    https://juce.com/learn/tutorials
    


-end-
