# rox-wrappers

(c) 2012 Nick Booker

A collection of program wrappers I find useful.

These could just be simple AppFactory wrappers for graphical tools, or
wrappers that call command line programs and provide a GUI of some sort
(whether a savebox or something more complicated).

## Kindle

The Kindle wrapper will attempt to download from Amazon and install the
Windows program under Wine in your home directory, under ~/.kindle-rox/wine

Don't complain to Amazon if this wrapper doesn't work.

Because of Amazon's software terms of use, I can't distribute the installer
or an extracted version of it, so this script has to download the file
directly from Amazon.

It's likely that the download URL for the Amazon installer will change, so
if the download step fails, first try adjusting the
variable ```$DOWNLOAD_URL``` to the exact download URL provided by
Amazon.

If that still fails, try downloading the installer yourself, and run:

```
mkdir -p "${HOME}/.kindle-rox/wine"
export WINEPREFIX="${HOME}/.kindle-rox/wine"
winetricks vcrun2008
wine "path/to/KindleForPC-installer.exe"
```

Then test yourself:

```
export WINEPREFIX="${HOME}/.kindle-rox/wine"
wine "${WINEPREFIX}/drive_c/Program Files/Amazon/Kindle/Kindle.exe"
```

If that still fails, see if there's a bug on the WineHQ bug tracker.

Amazon will likely not want to know if their software fails to run
through this wrapper; and chances are they won't want to know about Wine
or Linux either.

## Debian\_Packages

Some of the wrappers contain a file ```Debian_Packages``` which documents
the names of the package(s) you need to install in Debian in order for
the programs to run.
