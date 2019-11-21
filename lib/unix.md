system config
Processes
Network
Shell scripts
Dev tools
Moving files


bin/sh => shell program, executes scripts (simular to BAT files)
find/locate

Shell vars
  assign:		BAR = Foo
  access:		$BAR
  make it env var: 	export BAR

cmd path
err messages
kill process

symbol links
permissions
zip

usr dir
sudo

        hardware: (CPU, RAM, Disks, Network)
           /\
          /  \
         /    \
        /      \
       ----------
     process  kernel: (System calls, manages hardware)
       ||
       \/
 GUI, shell, servers


Kernel mode Vs user mode (k/u space)
RAM access and CPU operations => kernel mode

RAM => '01' where kernel processes run, (main memory)
CPU => `operates` on RAM takes input from RAM and writes on RAM
state => image (arrangement of bytes)


Processes:	    Kernel decides which process to use CPU
Memory:		      Kernel keeps track of everything in the RAM
Device drivers:	Kernel is the interface to the hardware
System calls:	  Processes communicate with the kernel through sys calls


MMU => Memory Management Unit
virtual memory
memory address map
memory performance


kernel creates identical copy of the process
  /\
  ||
 fork()    exec(program) => kernel replaces current program with the passed program
    \      /
     \    /
      \  /
       \/
   sys calls


Start new process:
  shell -->  fork() --> shell
               |
               --> shell copy --> exec(process) --> process
  example => write `ls` in the shell


pseudodevises

user space => collection of running process

basic services => utilities servise - apps.

user => entity
  permissions
  name
  id

root => superuser, can read any file or terminate any process
  root access

groups => set of users

user processes => env - usr interface

Std I/O
  `ctrl - d` => stop stdin and terminate to curr process 

three streams => stdin, stdout and std err

The default output is the stdout

unix cmd take input and give output

cp, mv can work on multiple files

wildcard

$HOME

globbing . => one char
echo * => match anything
echo at* => startwith `at`

echo a?t => match one char ex.: act

grep => print the matching lines from a stream or files
  -i -> case insensitive
  / grep "pattern" /path/to/files/

                   ex.: "*str"
find {dir} -name {file_pattern}
chsh => change shell

append new command dir to cmd Path
  PATH = dir:$PATH

Edit shell cmd
  ctrl - b back one letter (ctrl left arrow)
  ctrl - f forward one letter (ctrl right arrow)
  ctrl - p previous cmd (up arrow)
  ctrl - n next cmd (down arrow)
  ctrl - w erase prev word (ctrl backslash)
  ctrl - y yank

man -k => search by keyword
cmd > file => redirect stdout and overrides file
cmd >> file => redirect stdout and appends it file

cmd > file 2 > error redir stdout in file and err stream in error
  stream id 1 => stdout
  stream id 2 => err stream

cmd < {path_to_file} => redirect stdin

Err msg components
  {program_name} {file_name} {err_msg}

PID => process id

ps => show current processes
  -x    curr usr processes
  -ax   all processes
  -u    detailed info
top => simular to ps, need to press keys

kill pid => stops processs by id
  -CONT
  -KILL
  -INT
  -STOP

Job Control

TSTP signal => ctrl - z
  fg -> bring foreground
  bg -> move background
  {cmd} {params} & => executes a cmd in background


File modes and permissions
  w - write
  r - read
  x - execute
  - - nothing

  ls -a =>
    -|rw-|r--|r--

        -       |   rw-  |    r--     | r--
   (file type)  |  user  |   group    | other
   
ln -s {target} {link_name} => creates a symlink


gzip tar

Directory hierarchy

root
  bin/ => ready to run programs, executables
  dev/ => device files
  etc/ => core sys config dir [pwd, boot, device, networking]
  usr/ => root stuf, no usr things
    bin/
    man/
    lib/
    local/
    sbin/
    share/
  home/ => personal dirs
  lib/  => static or shared ??
  sbin/ => sys executables
  tmp/  => tmp files, periodically cleaned
  var/
    log/ => record process runtime info
    tmp/

Other dirs
  /proc  => sys stats
  /sys   => sim to /proc
  /boot  => kernel loader files
  /media => flash drivers
  /opt   => third party software


cmd at => schedule task in the future

lsof => lists open files

socket, network, connection, pipe

strace => trase all sys calls a program do
thread => simular to process, but share resourses

ps m => show process and threads
resourses => CPU time, memory and disk I/O

memory pages
page swaps
page fauts: MINFL and MAXFL

Monitoring: vmstat and iostat


packets => headers (origin, dest) and payload (actual data)

	
Network stack -> consists of layers
  App layer
    HTTP - web
    SSL  - Secure Socket Layer 
    FTP  - File Transfer Protocol
  Transport Layer
    TCP  - Transmission Control Protocol
    UDP  - User Diagram Protocol
  Internet (network) layer
    IP   - Internet Protocol
  Physical layer

                 Subnet

                  LAN
                  ||
                  \/
    ---------------------------------
    |          |          |         |
 Host A     Host B      Host C    Router <----> Internet

Host => computer, can be connected to one or more subnets
Subnet => smaller network (set of connected hosts)
Internet => many subnets connected together
Router => host that enables data transfer (gateway). Has address for the subnet and link to internet (10.232.37)

ifconfig => lists usr ip addresses

subnet = {mast} + {network prefix (what is in common)}
mask 255.255.255.0    11111111 11111111 11111111 00000000
prefix 10.23.2.0

subnet ex.: 10.23.2.0/255.255.255.0 -> subnet 10.23.2.[0..255] possible ips in this subnet

route -n => routing table
default gateway

ICMP => Internet Control Message Protocol
DNS  => Domain Name Service (maps names to ips)

ping => debug tool

Ethernet Network - MAC (Media Access Control) = hardware address

TPC => Transmission Layer Protocol (most used)
UDP => User Diagram Protocol

Network metaphor
  IP   => building address
  Port => mailbox number

netstat -n => show open connections
connection => server is listening and the client is connecting

======================================================================
============================= HTTP articles ==========================
how does the browser opens the socket
from where does he get the server address and the port

TCP
  error detection
  flow control
  overall reliability
  gurantee delivery
UDP
  User Diagram Protocol
  does not gurantee delivery
IP
  does not gurantee delivery

Persistent Connections

`tail -f *.log` -> nice way to watch for all log files

`cd -` -> go back to the previous dir

Remove old leftovers from packages
`sudo apt-get autoremove --purge`

you can find a package on the net, download it and install it

find a package on the end
  `{package-name} .deb {distribution}` ex.: `exuberant-tags .deb 16.04`


Debugging ubuntu packages
dpkg --status libpq5
pg_config --pkglibdir

grep for a string among all files
  find -type f -print0 | xargs -0 grep SEARCHED_STRING
