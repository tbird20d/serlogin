# serlogin - Serial port login program
This program is intended to be used in conjunction with serio
(see https://github.com/frowand/serio) to provide complete
support for handling a Linux machine over a serial port in
an automated fashion.

This program supports logging in to a machine over it's serial
port - when that port is at a serial console, and the result
of logging in is that the machine runs a shell prompt.

Commands needed on the target machine are: ls, grep, and id.

# Installing
To use serlogin, place it somewhere on your path (usually somewhere
like /usr/local/bin), and make sure you have python and the python
serial module installed.

As of 2017, most modern Linux desktop distributions include the python
serial module with the default installation of python.

# Running
serlogin supports lots of options for specifying serial port settings.
See the usage for information about options.
Usage for serlogin is available with '-h'.

Here are some examples:

   $ serlogin -d /dev/ttyUSB0 root

Login as root to the machine connected to the serial port ttyUSB0

   $ serlogin -d /dev/ttyACM1 -P mypassword user1

Login as user1, using password 'mypassword' to the machine connected
to serial port /ttyACM1

serlogin assumes that the login prompt has the string 'login:' in it.
If your machine uses some other login prompt, you can specify it on
the serlogin command line with the '-l' (or '--login-prompt') option.

# Debugging
The algorithm used by serlogin is fairly simple, but if you run into
trouble, you can turn on debugging with the option '--debug' on the 
command line.  It is also sometimes useful to use serlogin with 'strace'
to see the exchange of data between serlogin and the remote machine.

Good Luck,
 -- Tim Bird
