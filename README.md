# Tix mingw64 build instruction
An extension of tk (or ttk), tix contains a valuable UI element to my project: a tree structure with checkboxes and icons per each item. It also has scrollbar-enabled widgets. Plus, it's very small in size.
Again, you can find it in bawt's tcl3d package:

http://www.bawt.tcl3d.org/preview.html

Here is the source code, if you really want to build it from scratch (also on bawt site):

http://www.bawt.tcl3d.org/download.html

Search for "Tix". Only one version: 8.4.3.

Check my README.md instruction for vtk_tcl_tk_build_support repo if you are not familiar with Windows' mingw64 and cmake-gui

20211210: rebuilt tix from scratch.
- Need to modify tix configure file, line 2229, from:

<code>	*win32*|*WIN32*|*CYGWIN_NT*|*CYGWIN_9*|*CYGWIN_ME*|*MINGW32_*)</code>

to:

<code>	*win32*|*WIN32*|*CYGWIN_NT*|*CYGWIN_9*|*CYGWIN_ME*|*MINGW32_*|*MINGW64_*)</code>

Tix is too old to support mingw64, and yet it works.


- Make sure to add the following configure options:

<code>--prefix=<install_directory_for_tix></code> (seems to be ignored. Tix was eventually installed into install_tcl/lib directory for me)

<code>--enable-threads</code>
  
<code>--enable-64bit</code>
  
<code>--with_tcl=<tcl_build_directory></code>
  
<code>--with_tk=<tk_build_directory></code>
