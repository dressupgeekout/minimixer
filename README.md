# Minimixer

This is a stupid-simple loop machine and/or live sequencer. You create loops
beforehand, then load them into this program and play them with just a few
keystrokes. It should be able to apply crazy effects whenever you want but
that won't be for a while, I'd imagine.

Minimixer is written in Ruby (it really should be written in C) and relies
on Curses and NAS, but it only works on Unix-like operating systems.  That's
because we achieve concurrency with plain, old-fashioned fork-and-exec.
Also, loops are somewhat manipulated with the help of signals. So there's no
way Microsoft Windows (for example) could handle this program the way it's
designed.


## Usage

You're expected to create loops (small audio files, ideally of the same
length) beforehand. Then you write a text file wherein the paths (relative
or absolute) to these loops are provided, one per line. The minimixer(1)
utility expects this file to passed in on the command line.

When Minimixer starts up, it assigns a key to each loop. The order of keys
is predictable: it's the QWERTY alphabet (the first loop is "q", the next is
"w", and so on).

Minimixer stars with no loops playing. To play a loop, press its appropriate
key. To stop a loop, press the upper-case version of the key. So "q" plays
the first loop and "Q" stops it.

To quit the progam, type "!". This will stop all loops if you have not done
so already.


## Tips and tricks

It's recommended that you arrange your loops hierarchically. Leverage your
file system! If you have many different drum loops, put them in a directory
called "drums" or something. That way they show up in Minimixer as
"drums/blah1" and "drums/blah2".


## Thanks

Big thank you to the Laptop Musician Workshop and the Hacker Dojo for
support and feedback!


## License (2-clause BSD-style)

Copyright (c) 2013 Christian Koch.
All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

  - Redistributions of source code must retain the above copyright notice,
    this list of conditions and the following disclaimer.

  - Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in the
    documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE
LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.
