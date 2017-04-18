===========================================
Babelzapper Version 4.4
by gutemine 
===========================================
Release infos 
===========================================
4.4	OE2.5 support and architecture all
4.3.0	OE2.2 support
1.1.0	Audio support
1.0.0	make new cvs version
===========================================

Installation:
-------------

First copy the file enigma2-plugin-extensions-babelzapper*.deb
to /tmp with ftp (TCP/IP must be working already). 

Then install Babelzapping by entering the 
following commands in a Telnet session:

cd /
dpkg -i /tmp/enigma2-plugin-extensions-babelzapper*.deb

You can remove Babelzapper with the red button in the Plugin List,
or the Softwaremanager Plugin of enigma2,
or with the following command in telnet:

dpkg -r enigma2-plugin-extensions-babelzapper

Usage:
------

The Babelzapper plugin allows you to control 
your Dreambox completely with a single RC button,
the mute button.

If the Plugin is enabled and you press the mute 
button the Babelzapping Command Button 
will appear in the upper middle of the TV screen.

It then simply srolls trough the appropiate 
remote control buttons as defined in the babelzapper.zbb
file, and if you press the mute button
again the choosen remote control button
or other babelzapper commands as defined in the
babelzapper.zbb file will be executed.
When you choose NONE (which executes STOP)
you can exit without executing a command.

The speed of button scrolling is adjustable
in the Babelzapper Plugin.

The real mute button is disabled 
when you enable the Babelzapper,
use volume down to mute instead of this.

For adapting the commands available for execution
edit the babelzapper.zbb file at /tmp/babelzapper

zBABEL Language:
---------------

The first text at the beginning of the line in the
babelzapper.zbb file is always the label as shown
on the TV screen when scrolling through the command
lines of the babelzapper.zbb file.

For the correct key names of your remote control
have a look at the provided
examples in the babelzapper.cfg
file or at /usr/lib/enigma2/python/keyids.py
for the full list of available keys.
Keycodes are always writen with $KEY_LABEL
and will be replaced by the apropiate keycodes
as found in the keyids.py file.

If you add _LONG to the keyname (for example
$KEY_BLUE_LONG) the keycode will be executed 
as long press, and you can spefify
multiple keycodes to be 
sequentially executed from left
to right and other babelzapper commands
as explained below when they are 
seperated with the ";" 

The first text at the beginning of the line in the
babelzapper.zbb file is always the label as shown
on the TV screen when scrolling through the command
lines of the babelzapper.zbb file.

Other commands supported are:

GOTO	linenumber
STOP	miliseconds (from 1000 to 60000)
REM	remarking text
RETURN	linenumber
PRINT	text for the TV screen
END	exit scrollmode
LOAD	menufile
RUN	menufile
ON	on flag enable and continue if enabled
OFF	on flag disable

A line with a GOTO has to be executed 
by pressing Mute, but GOTO can also be
used at the end of a line with other 
commands. This can be used for
jumping into all areas of the 
babelzapper.zbb file.

If you edit the babelzapper.zbb file on a PC 
it is wise to use an editor which shows 
you the linenumbers to simplify identifying
the correct linenumbers. Be aware
that line 0 is a NONE with the END command
which is hardcoded and not in the babelzapper.zbb
file.

RETURN is a jump to the specified
linenumber which gets executed 
when reached during the scrolling
of the commands and doesn't need to be selected 
(it is not even shown on the TV). 
Hence RETURN cann be used to jump
back from submenus entered with GOTO.

If you don't specifiy a linenumber
for RETURN or GOTO always 0 will be used.

You can now also add colors to the button label
by using LABEL:x:y

with x the background color and y the foreground color
with the following values:

black	0
white	1
grey	2
red	3
green	4
yellow	5
blue	6

The zBABEL script language used in 
the babelzapper.zbb file
is a little bit like good old BASIC, 
so keep in mind the typical
recommandations for it like commenting your code
with REM lines, using tabs and/or blanks
to increase readability
and especially use GOTO and RETURN with care and 
wisdom.

=======================================================
Have fun using Babelzapper on your Dreambox
=======================================================
