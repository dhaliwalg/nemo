Introduction
============

NEMO is a collection of programs, running under a standard UNIX shell,
capable of running various stellar dynamical codes and related
utilities (initialization, analysis, gridding, orbits).  It can be
thought of as a collection of various *groups* (packages) of
programs, a group being defined by their common file structure.

.. A % common low level file structure is defined, which is then shared by all
   groups.  This lowest file structure eventually interacts directly with
   the data on disk.

A common (command line) user interface is defined with which the user
communicates with a program, described in more detail in the next chapter
:ref:`iface`.
   
..   and  Appendix~\ref{a:iface}.  

In order to run NEMO programs, your shell environment has to be modified.
See :ref:`using` on how to setup NEMO.
Appendix~\ref{a:setup} gives a full description. Installation is covered
elsewhere.


Let us first give you an overview of the various *groups* of programs,
as they clearly show the structure of NEMO:

- The *N-body group*
  is defined by a common file structure of *snapshots*.
  In this group we find various programs
  to create N-body systems (spherical, elliptical, disk), methods to compute the
  gravitational field (softened Newtonian, hierarchical, Fourier
  expansion), and time-integrators (leapfrog, Runge-Kutta).  Many
  utilities exist to manipulate, analyze and display these data.

- The *Orbit group* is defined by a common file structure of
  *orbits*.  It is mainly intended to
  calculate the path of an individual orbit in a static potential and
  then analyze it.  This group is closely related to the before
  mentioned N-body group, and utilities in both groups can interact
  with each other.  For example, it is possible to freeze the
  potential of an N-body snapshot, and calculate the path of a
  specific star in it, now conserving energy exactly. Or to extract
  the path of a selected star in a simulation, and extract an orbit from it.

- The *Image group* is defined by a common file structure of
  *images*, i.e. two dimensional
  rectangular pixel arrays with a 'value' defined for every pixel.
  Actually an image may also have a third axis, although this axis
  often has a slightly different meaning *e.g.* Doppler velocity.
  It is possible to generate arbitrary
  two-(and three-) dimensional images from snapshots, FITS files
  of such images can be created, which can then be
  exported to other familiar astronomical data reduction packages.
  There exists a variety of programs in the astronomical community to
  manipulate data through the FITS format.

- The *Table group* appears quite commonly among application
  programs in all of the above mentioned groups.  Most of the time it
  is a simple ASCII file in the form of a
  matrix of numbers (like a spreadsheet).  A few programs in NEMO can
  manipulate, display and plot such table files, although there are
  many superior programs and packages outside of NEMO available with
  similar functionality. It is mostly through these table files that
  we leave the NEMO environment, and persue analysis in a different
  environment.  The obvious advantage of storing tables in
  binary form is the self-documenting nature of NEMO's binary
  files. For historical reasons, most tables are displayed and created
  in ASCII, though you will find a few binary tables as well.


More groups and intermediate file structures are readily defined, as
NEMO is also an excellent development system.  We encourage users to define 
their own (or extend existing) data structures as 
the need arises.  In Chapter \ref{c:progr} we
will detail some 'rules' how to incorporate/add new software into the
package, and extend your NEMO environment. 

The remaining chapters of this manual outline various
concepts that you will find necessary to work with NEMO.
Chapter :ref:`iface` outlines the user interface (commandline, shells
etc.), details  are deferred to Appendix~\ref{a:iface}.
Chapter :ref:`filestr` explains how data is stored on disk and can be
manipulated, including the concept of function descriptors in NEMO.
Chapter :ref:`graphics` details how data can be
graphically displayed, either using NEMO itself or external programs.

The second part of the manual is a cookbook: Chapter~\ref{c:examples}
gives a variety of examples of use.

The third part of the manual is the programmers manual:
Chapter~\ref{c:progr} is for the more adventurous user who wants to
modify or extend NEMO. 

..  Some rules are given to increase the chance of upgrade survival. 

The last part of the manual are Appendices with a large variety of
reference information.

See :ref:`using` on how to setup NEMO in your shell environment.
