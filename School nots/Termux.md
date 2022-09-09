Termux is a free and open source terminal emulator for Android which allows for running a Linux environment on an Android device. In addition, various software can be installed through the application's package manager.
Termux installs a minimal base system automatically, and additional packages are available using a package manager.
Most commands available in Linux are accessible as well as built-in Bash commands. There are also several other shells available, such as Zsh and tcsh.Termux is the first Android terminal application to include a variety of software, unlike other terminal emulators, in which only small or limited utilities provided by Android are available.


== Overview ==
Packages are cross-compiled with Android NDK and have compatibility patches to get them working on Android. Since all files are installed at the application directory, rooting is not required.There are more than one thousand packages that can be downloaded and users can submit requests for new ones.
Alternatively, packages can be compiled from source as Termux supports a variety of build tools including CMake as well as compilers for C++, Rust, Go and several others.
Termux can also install interpreters for languages like Ruby, Python, JavaScript, etc.
Terminal-based text editors such as Emacs and Vim can be installed to edit and create files from the terminal.
It is also possible to execute GUI applications in Termux through a VNC server and installing a desktop environment (Xfce, LXQt, MATE) or window manager.


=== User interface ===
Termux's user interface is fairly simple and only displays extra keys row and the terminal output, managing sessions by swiping left and manipulating Terminal session by tap and holding and clicking more to bring 10 options. It is also possible to change the color scheme and font through Termux:Styling.
Extra keys row can also be customized. Users can add more function keys and controls within termux.properties file
Termux also has mouse/touch support which can be used to interact some programs that can be used with mouse such as htop and other ncurses-based applications, scrolling is also be done by swiping over terminal buffer.


=== Configuration ===
Users can configure the Terminal within termux.properties file. unlike other Terminal emulators, Termux's configuration is read within that file instead of using graphical settings which users will have to use a text editor.


=== Add-ons ===
Termux also includes 6 add-ons:

Termux:API: exposes Android functionality to CLI applications
Termux:Styling: allows to change the colorscheme and the font of the Terminal
Termux:Boot: executes Termux commands at boot
Termux:Widget: let's users to run scripts in a dedicated widget or a shortcut in Home screen
Termux:Float: runs Terminal session in a floating window
Termux:Tasker: Plugin to integrate Tasker app to TermuxAdd-ons must be installed from same source, as add-ons signed with same signature key to use have same User ID between these apps


== History ==
Termux was initially released in 2015. At its initial launch, it already included a variety of Linux software. Support for requesting packages and features was added through GitHub issues in the app's repository. People can also contribute to the project by adding new features and packages.
In January 2020. Termux development team ended support for devices running Android 5-6 and Termux required Android version 7 as a minimum OS requirement.
With the policy changes in Google play policies, updates to the app through playstore are no longer possible and as such, it is recommended to install the app through alternative sources.
As of 2021 Termux is maintained by collaborators and the current development were behind Fornwall's maintenance to the app


== Installation ==
During the installation, it extracts the bootstrap archive from the APK file and set correct permissions for executable and sets up directories like home directory.


== Package management and distribution ==
Packages in Termux are installed through the application's package manager (pkg) and uses the .deb format by default. But normal Debian packages cannot be installed as Termux is not FHS compliant.
Users can also build and submit packages.
