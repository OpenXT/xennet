XenNet - The Xen Paravitual Network Device Driver for Windows
=============================================================

The XenNet package consists of a single device driver:

*    xennet.sys is an NDIS6 miniport driver which attaches to a virtual
     device created by XenVif and uses the *netif* wire protocol
     implementation in XenVif to interface to a paravirtual network
     backend. 

Quick Start Guide
=================

Building the driver
-------------------

First you'll need a device driver build environment for Windows 8. For this
you must use:

*   Visual Studio 2012 (Professional or Ultimate)
*   Windows Driver Kit 8

(See http://msdn.microsoft.com/en-us/windows/hardware/hh852365.aspx). You
may find it useful to install VirtualCloneDrive from http://www.slysoft.com
as Visual Studio is generally supplied in ISO form.

Install Visual Studio first (you only need install MFC for C++) and then
the WDK. Set an environment variable called VS to the base of the Visual
Studio Installation (e.g. C:\Program Files\Microsoft Visual Studio 11.0) and
a variable called KIT to the base of the WDK
(e.g. C:\Program Files\Windows Kits\8.0). Also set an environment variable
called SYMBOL\_SERVER to point at a location where driver symbols can be
stored. This can be local directory e.g. C:\Symbols.

Next you'll need a 3.x version of python (which you can get from
http://www.python.org). Make sure python.exe is somewhere on your default
path.

Now fire up a Command Prompt and navigate to the base of your git repository.
At the prompt type:

    build.py checked

This will create a debug build of the driver. To create a non-debug build
type:

    build.py free

Installing the driver
---------------------

See INSTALL.md

Driver Interfaces
=================

See INTERFACES.md

Miscellaneous
=============

For convenience the source repository includes some other scripts:

kdfiles.py
----------

This generates two files called kdfiles32.txt and kdfiles64.txt which can
be used as map files for the .kdfiles WinDBG command.

sdv.py
------

This runs Static Driver Verifier on the source.

clean.py
--------

This removes any files not checked into the repository and not covered by
the .gitignore file.
