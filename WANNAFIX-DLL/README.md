# WANNAFIX DLL

See https://github.com/HIBC2017/WANNAFIX/pull/3 for further information!

## WANNAFIX DLL USAGE

Simple really - from any .bat or .ps1 script, you can just call rundll32 to run the file:

`rundll32 \\path\to\WANNAFIX.dll,0`

Note that the comma-0 at the end doesn't do anything, but it's required for rundll32 to work, so make sure you keep that in!

## How does it work?

Rather than sending/running an executable file across the network, you can also host a single .dll file and have this accessed from a file share by a script running as admin. 

This subdirectory contains a compiled WANNAFIX.dll file as well as the source for the file. This does everything that the main .exe does, but _without_ the interaction being required. 

**NB** - This dll **does not** shut the machine down; you'll have to do that manually to disable SMBv1. Or, you can uncomment the restart line and recompile (see the WANNAFIX-DLL.cpp file for how to compile under linux), but this won't add the mutex on reboot. 

**As with the WANNAFIX.exe file, this is only a temporary fix, albeit one that can easily be widely deployed.**

Many thanks!

## UPDATE

Now includes the creation of the NULL file required to prevent Petya from starting!