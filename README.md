Comms
=====

A text-mode user interface to Audacious audio player, forked from Ulf
Betlehems's cplay in January 2002. Further history and documentation is available at the project homepage http://iki.fi/teknohog/hacks/comms/.

Originally, Comms was simply a text-mode user interface, because I
preferred it to graphical controls. As such, it also works as a handy
"remote control" over ssh.

However, over the years it gained a couple of quirky features to
scratch my own itches as a DJ / sound guy of a student theatre:

* Cache files to hard drive -- to compile a playlist from files burned
  to different CDs

* Hotkeys for playing each of the first 22 tracks -- for playing sound
  effects on demand for (improvisational) theatre

* Fade out and stop

Since version 3.5, Audacious uses the newer GDBus framework. This
mandated a change from the python-dbus library to pydbus:

https://github.com/LEW21/pydbus

This library had some random timeout issues with Audacious. They were
fixed by changing the timeout=10 to 100 in pydbus/bus.py. This problem
is still apparent when using Comms to start Audacious, but it is not
recommended anyway, for reasons such as error messages clogging the
terminal.
