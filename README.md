# gooverlay

It is a small library to simulate a overlay mount.

Given two directories, bottom and top, gooverlay applies top on bottom.

If the top directory contains whiteout files, `.wh.$filename` the respective file in the bottom directory get deleted.

If the top directory contains opaque whiteout directories, directories containing a `.wh..wh..opq` file, all the content of that specific bottom directory get deleted.

Special care is taken to give the owner of the file and of the directory permission to always modify the directory, at the cost of not following a 100% accurate overlay model.

This simulate what docker and other container runtimes do in order to create the filesystem strting from layers.
