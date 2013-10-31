ghpsdr3-fcdpro-server
=========================

It is Funcube Dongle Pro (1.0) server for ghpsdr3-alex implementation on python.

Dependencies is:
 - python-alsaaudio
 - python-numpy
 - https://github.com/bazuchan/cython-hidapi (fork of https://github.com/gbishop/cython-hidapi)

Todo:
 - support for multiple receivers (it's incomplete).

Basic usage:
 - run fcd-server.py
 - run dspserver
 - run QtRadio

Predsp:
If you want to run fcd-server.py on embedded hardware (like BeagleBone Black in my case),
you probably would want to move all data preprocessing (eg. conversion from ints to floats)
to host running dspserver. For that purpouse I wrote small script called predsp.py. Usage:
 - on embedded host run 'fcd-server.py -p'
 - on more capable host run 'predsp.py' and 'dspserver --server <embedded host ip>'
 - run QtRadio or another client and point it to dspserver's address

