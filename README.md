# bash-cheetsheet-gisheet
The most helpful bash terminal cheatsheet for help
Skip to content
Search or jump to…
  
##############################################################################
// BASH CHEATSHEET (Chinese Cheat Sheet)-by skywind (created on 2018/02/14)
// Version: 47, Last Modified: 2019/09/24 17:58
// https://github.com/skywind3000/awesome-cheatsheets
##############################################################################


##############################################################################
#Commonly used shortcut keys (Emacs keys are used by default)
##############################################################################

A + the CTRL               # moves to the beginning of the line, with the <Home>
B + the CTRL               # moved backward, with <Left>
C + CTRL               # end of the current command
D + CTRL               # delete the character before the cursor with the <Delete>, or when there is no content, exit the session
E + the CTRL               # moves to the end of the line, with <End>
CTRL+F               #Move forward, same as <Right>
G + CTRL               # exit the current editor (such as when your search history is CTRL + R)
H + CTRL               # delete the character left of the cursor, with <Backspace>
K + CTRL               # delete the contents of the cursor position to end of line
L + CTRL               # clear the screen and redisplay
N + the CTRL               # moves to the next line of command history, with the <Down>
CTRL+O               #Similar to carriage return, but will display the next line of history
+ P the CTRL               # moves to the line of command history, with <Up>
R + CTRL               # history commands reverse lookup, use CTRL + G to exit the search
S + CTRL               # history forward search command, use CTRL + G to exit the search
T + CTRL               # before and after the exchange of two characters
U + CTRL               # delete the character to the beginning of the line
CTRL + V               # input character literals, press CTRL + V and press any key
W + CTRL               # delete a word left of the cursor
The X-+ CTRL               # lists the possible completions
The Y + the CTRL               # paste front CTRL + u / k / w content deleted through
The Z-+ CTRL               # suspend the foreground process returns bash, available fg to switch it back to the front desk as needed
CTRL + _               # Undo (undo), and some terminal CTRL + _ mapped CTRL + / or CTRL + 7

B + ALT                # backward (left) one word
D + ALT                # After you remove the cursor (to the right) a word
F + ALT                # forward (to the right) to move a word
T + ALT                # swap characters
+ BACKSPACE ALT        # delete the cursor in front of a word, similar to the CTRL + W, but does not affect the clipboard

The CTRL + + X-X-the CTRL        # press twice CTRL + X, the cursor jumps back and forth in the first position and the current row
The X-CTRL + E + CTRL        # with your specified editor to edit the current command


##############################################################################
# BASH basic operation
##############################################################################

Exit                 # exit the current landing
env                  # display environment variable
echo  $ SHELL          # show you what SHELL

bash                 # using bash, returns with exit
bash Which           # search $ PATH, find out which program corresponding to the command bash
bash whereis         # search for executable, the location of the header files and help information, use the built-in database system
bash whatis          # View explain a command word to tell you this is doing

the Clear                # early Qing screen content
the RESET                # Reset terminal (when you do not accidentally use cat a binary, terminal status mess)


##############################################################################
# Directory operations
##############################################################################

cd                   # to return to their $ HOME directory
CD {dirname}         # into the directory
pwd                  # Display the current directory
{dirname} mkdir      # Create a directory
-p} {dirname mkdir   # recursively create directories
the pushd {dirname}      # directory into the new directory and push
the popd                 # pops up and into the top of the stack directory
dirs -v              # list the current directory stack
cd -                 # back to the previous directory
CD - {N}              # change to the directory stack N-directory, such as cd -2 to switch to the second


##############################################################################
#File operations
##############################################################################

LS                   # display the current contents of the directory, the directory name can be followed: ls {dir} displays the specified directory
the -l LS                # display a list of directory contents, information includes file date, size, permissions, etc.
-1 LS                # display a list of contents of a directory, only the file name, followed by a minus sign is the number 1
-a LS                # show all files and directories, including hidden files (files that start / directory name)
{} {-s the Fn LN Link}    # create a soft link to the specified file
{} {dest the src CP}      # copies of documents, cp -r dir1 dir2 recursively copy (directory)
RM the Fn} {              # delete files, rm -r recursively delete the directory, rm -f forced to delete
{} {dest the src Music Videos}      # move a file, if dest is a directory, move, the file name is covered
Touch the Fn} {           # create or update about the development of file
{Fn} CAT             # output file original content
any_cmd > {Fn}       # execute commands and standard output to the specified file
{Fn} More            # -by-screen display contents of a document, page space, q exit
{Fn} less            # more advanced more points, more operations, q exit
{Fn} head            # show the number of lines the file header, it can display the first three rows head -3 abc.txt
{Fn} tail            # show the number of rows end of the file, display the available aft three rows tail -3 abc.txt
{Fn} -f tail         # continues to display end of the file data, to monitor the log
nano Fn} {            # use nano editor to edit the file
{Fn} vim             # used to edit the file vim
{F1} {F2 the diff}       # compare the contents of two files
the Fn} {WC              # statistical document how many lines, how many words
{Fn} 644 the chmod       # modify the file permissions 644 can then access to the directory cycle change -R
Group {Fn} chgrp     # groups to modify the file belongs
{Fn} user1 chown     # modify the file owner is user1, chown user1: group1 fn can modify group
{Fn} File            # type and code detection files
basename the Fn} {        # see the name of the file (not including the path)
dirname the Fn} {         # view the file path (not including the name)
{pat the Fn} {grep}      # in the file appeared to find the content of pat
-r pat} {grep .      # recursive search all the content files appeared pat in the current directory
{Fn} STAT            # detailed information display file


##############################################################################
#User Management
##############################################################################

whoami               # show my username
the WHO                  # Displays the user login information, w / who / users slightly different content
w                    # Displays the user login information, w / who / users slightly different content
the Users                # Displays the user login information, w / who / users slightly different content
the passwd               # Change Password, passwd {user} others may be used to modify the root password
} {User finger        # displays a user information including id, name, login status
User} {the adduser       # Add User
} {User deluser       # delete user
w                    # to see who is online
SU                   # to root
su-                 # Switch to root user and log in (execute login script)
} {User SU            # switches to a user
SU -} {User           # switches to a user and log (login script execution)
} {User ID            # view the user's uid, gid, and other relevant user groups
-u} {User ID         # Print User uid
-g} {User ID         # Print User gid
} {User Write         # send a message to a user
Last                 # to display a list of recent user login
} {User Last          # display record login
lastb                # display failed login records
lastlog              # Show last login records for all users
Command the sudo} {       # execution of a command as a root


##############################################################################
# Process Management
##############################################################################

PS                         # to view the current Session
AX PS                      # view all processes, similar to the ps -e
the AUX PS                     # to view details of all processes, similar to the ps -ef
auxww PS                   # view all processes, and displays the complete command to start the process
-u the User} {PS               # view a user process
axjf PS                    # List processes tree
-u} {User XJF PS           # are listed in a user's process trees
-EO pid PS, the User, the Command    # according to user-specified format to view the process
the AUX PS | grep httpd        # View all the processes named httpd
--ppid} {pid PS            # View parent process for all process pid
pstree                     # tree lists all the processes, pstree default generally do not take, install
User} {the pstree              # process tree lists a user process
-u pstree                  # tree lists all the processes and their user
procname} {pgrep           # pid search name matching process, such as pgrep apache2

the kill {pid}                 # end of the process
the kill -9 PID} {              # terminates the process, 9 / SIGKILL capture end signal is not mandatory
the kill -KILL PID} {           # enforcement process, kill -9 Another way to write
the kill the -l                    # View all signals
the kill the -l TERM               # view the number of signal TERM
procname} {killall         # by name ending all processes
procname} {pkill           # by name end of the process, there can be other parameters except name

Top                        # view the most active processes
-u} {the User Top              # view a user most active processes

Run any &              # running in the background of a command, CTRL + Z will also be linked to the current process to the background
Jobs                       # View all background processes (jobs)
BG                         # view background process, and switch over
fg                         # to switch back to the foreground process
FG {} Job                   # handover to a particular foreground background processes

Trap cmd Sig1 SIG2         # Set the signal processing command in a script
Trap  " " Sig1 SIG2          # mask a signal in the script
Trap - Sig1 SIG2           # restore the default behavior Signal Processing

the Command} {nohup            # long run a program, you have to keep it running log out
the Command} {nohup &          # long run a program in the background
the disown {PID | JID}           # the process is removed from the list of background tasks (jobs)

the wait                       # wait for the end of all background processes tasks


##############################################################################
# Commonly used commands: SSH / System Information / Network
##############################################################################

user @ host SSH              # user-user log in to a remote host host
-p {} the User Port SSH Host @    # designated landing port Host
Copy the User-the above mentioned id-SSH Host @      # copy your ssh key to the remote host, avoid entering password
{Fn} User @ SCP Host: path    # copy the file to the remote host
the User @ Host scp: dest path    # back copy files from a remote host
-P {Port} ... SCP          # specified port remote copy file

-a uname                   # Viewing the kernel version, etc.
Help} {man                 # view help
-k {keyword} man           # view help files which contains the keyword
{} Help info                # View info pages, stronger than man's help system
Uptime                     # View system startup time
DATE                       # display date
CAL                        # show calendar
vmstat                     # display memory and CPU usage
10 the vmstat                  # print a line every 10 seconds where memory and CPU, CTRL + C Exit
as Free                       # show memory and swap usage
df                         # show disk usage
du                         # Display the current directory occupied, du. --max-depth = 2 can specify the depth
uname                      # Display system version number
hostname                   # show hostname
-a showkey                 # view the key code transmitted from the terminal

ping {host}                # ping the remote host and display the result, CTRL+C to exit
ping -c N {host}           # ping the remote host N times
Host} {the traceroute          # detect the connectivity route
Host} {mtr                 # advanced version of traceroute
host {domain}              # DNS query, add -a in front of {domain} to view details
Domain} {whois             # acquired domain information whois
Domain} {DIG               # acquired domain information dns
-n route                   # View the routing table
-a netstat                 # list all ports
-an netstat                # View all connection information does not resolve the domain name
-anp netstat               # View all connection information, including process information (requires sudo)
the -l netstat                 # View all listening ports
-t netstat                 # view all TCP links
-lntu netstat              # Display all is listening TCP and UDP information
-lntup netstat             # display all listening socket and process information
-i netstat                 # display card information
-rn netstat                # Display the current system routing table with route -n
-an SS                     # is faster than netstat -an more detail
-s SS                      # statistics of TCP established, wait, etc.

{} URL wget                 # download files may be added --no-check-certificate verification ignored ssl
-qO- URL} {wget            # download the file and to standard output (not saved)
{} URL -sl curl             # with wget -qO- {url} used when no wget

File} {SZ                  # send the file to the terminal, zmodem Protocol
Rz                         # receiving a file sent from the terminal


##############################################################################
# Variable operation
##############################################################################

value = varname              # define variables
value = varname the Command      # define sub-process variables and execute child process
echo  $ varname              # view the contents of the variable
echo  $$                    # to view the current shell process ID
echo  $!                    # View background tasks process ID of the most recent call
echo  $?                    # view the recent return code of a command
Export VARNAME = value       # Set environment variables (will affect the child process)

Array [0] = VALA              # definition array
array[1]=valB
array[2]=valC
array=([0]=valA [1]=valB [2]=valC)    # Another way
= Array (VALA Valb valC)                # another way

Array {$ [I]}                # acquired array element
{$ # Array [@]}               # acquired length of the array
{$ # Array [I]}               # obtain a variable length array

DECLARE -a                 # View all array
DECLARE -f                 # view all functions
DECLARE -F                 # view all functions to display only the function name
DECLARE -i                 # View all integers
DECLARE -r                 # See all read-only variables
DECLARE -x                 # See all be exported to the environment variable stuff
DECLARE -p varname         # output variables are defined by how (value + type)

{varname $ : - word}           # if the variable is not empty variable is returned, otherwise word
varname {$ : = word}           # if the variable is not empty variable is returned, otherwise assigning to a word and return
{varname $ :? the Message}        # if the variable is not empty variable is returned, otherwise print an error message and exit
{varname $ : + Word}           # if the variable is not empty then return word, otherwise return null
varname {$ : offset : len}      # made of a string

variable {$ # pattern}        # If the variable header match pattern, then delete the minimum matching the remaining portion to return
{variable $ ## pattern}       # if the variable head match pattern, then delete the largest part of the return match the rest of the
variable {$ % pattern}        # If the variable tail match pattern, then delete the minimum matching the remaining portion to return
{variable $ %% pattern}       # if the variable tail match pattern, then delete the largest part of the return match the rest of the
variable {$ / pattern / STR}    # will replace the first variable matching pattern into str, and returns
variable {$ // pattern / str}   # The variable pattern of all matches and returns the replaced str

{$ # Varname}                # Returns the string length

* (PatternList)             # zero or more times match
+ (PatternList)             # one or more times to match
? (PatternList)             # zero or one match
@ (PatternList)             # Word Match
! (PatternList)             # no match

array=( $text )              # Separate text into arrays by spaces and assign them to variables
IFS= " / " array=( $text )      # Separate the string text with slashes into an array and assign it to the variable
= text " $ {Array [*]} "         # with spaces link array and assigned to the variable
= text $ ( the IFS = / ;  echo  " $ {Array [*]} " )   # with slashes link array and assigned to the variable

= A (bar foo " ABC " 42 is) # array definition
= B ( " $ {A [@] : . 1 : 2} " )          # array sections: B = (bar "ab c ")
= C ( " $ {A [@] : . 1} " )            # array sections: C = (bar "ab c " 42)
echo "${B[@]}"            # bar a  b c
echo "${B[1]}"            # a  b c
echo "${C[@]}"            # bar a  b c 42
echo  " ${C[@] : -2 : 2} "       # abc 42 The space before the minus sign is required

$ ( UNIX the Command )            # run command and capture and return to the standard output content
varname = $( id -u user )      # Assign the uid of the user name user to the varname variable

= NUM $ ( expr. 1 + 2 )          # compatible posix sh calculation, the calculation result of using command expr
= NUM $ ( expr $ NUM +. 1 )       # number increment
2 expr \ *  \ ( 2. 3 + \)      # complex calculations posix sh compatible output 10

= NUM $ (( 1  +  2 ))             # calculates 1 + 2 is assigned to num, using bash unique $ ((..)) is calculated
= NUM $ (( $ NUM  +  1 ))          # variable is incremented
num = $(( num +  1 ))           #The variable is incremented, the $ in the double brackets can be omitted
= NUM $ (( . 1  + ( 2  +  . 3 ) *  2 ))   # complex calculations


##############################################################################
# Event indicator
##############################################################################

!!                   # previous command
! ^                   # The first word on a command
! :n                  #The nth word of the previous command
! : N-$                # on a command of the n-word to the last word
! $                   #The last word of the previous command
! -N: $                # the last word on the command n
! String              # recently a string containing the command
! ^ ^ String1 string2    # command contains string1 a recent, fast replacing string1 with string2
! #                   # All input before this command
! # :n # The nth word before this command, fast backup cp /etc/passwd !#:1.bak


##############################################################################
# Function
##############################################################################

# Define a new function
function  myfunc () {
    # $1 represents the first parameter, $N represents the Nth parameter
    # $# Represents the number of parameters
    # $0 represents the name of the callee itself
    # $@ represents all parameters, the type is an array, if you want to pass all parameters to other commands, use cmd "$@"
    # $* All parameters linked by spaces, the type is a string
    {shell commands ...}
}

myfunc                     # call the function myfunc
arg1 arg2 arg3 myfunc      # parameters of function calls
myfunc " $@ "                # Pass all parameters to the function
myfunc " $ {Array [@]} "       # an array of a plurality of parameters passed to the function as
the Shift                      # parameter to the left

unset -f myfunc            # delete function
DECLARE -f                 # list function definition


##############################################################################
# Condition judgment (judgment conditions compatible posix sh): man test
##############################################################################

statement1 && statement2   # and operator
statement1 || statement2   # or operator

exp1 -a exp2               # return true when exp1 and exp2 are both true (POSIX XSI extension)
exp1 -o exp2               # If one of exp1 and exp2 is true, return true (POSIX XSI extension)
(Expression)             # if expression is true returns true, the brackets before entering the note backslashes
! Expression               # If the expression is false that returns true

= str2 str1                # equal Analyzing strings, such as [ "$ x" = "$ y"] && echo yes
str1 ! = str2               # Analyzing string range such as [ "$ x"! = " $ y"] && echo yes
str1 < str2                # string is less, such as [ "$ x" \ < " $ y"] && echo yes
str2 > str2                # string is greater than, Note <or> is literal, to add the input backslash
str1 -n                    # is determined not empty string (length greater than zero)
str1 the -Z                    # determines string is empty (zero length)

File -a                    # Analyzing file exists, such as [-a / tmp / abc] && echo "exists"
File -d                    # determine the file exists and the file is a directory
File -e                    # determine the file exists, and -a equivalent
File -f                    # Analyzing file exists, the file and the file is a normal (non-directory)
File -R & lt                    # Analyzing file exists, is readable
File -s                    # Analyzing file exists, and the size is greater than 0
File -w                    # judge file exists and is writable
File -x                    # determine the file exists, and execute
File -N                    # after the file was last modified has not been read
File -O                    # file exists and is owned by the current user
File -G                    # file exists and matches your user group
-nt file2 file1            # file 1 to file new 2
-ot file2 file1            # file 1 to file 2 Old

-eq num2 num1              # digital judgment: num1 == num2
-ne num2 num1              # digital judgment: num1 = num2!
-LT-num2 num1              # digital judgment: num1 <num2
-le num2 num1              # digital judgment: num1 <= num2
-gt num2 num1              # digital judgment: num1> num2
-ge num2 num1              # digital judgment: num1> = num2


##############################################################################
# Branch control: if and classic test, posix sh compatible with the conditional statement
##############################################################################

test {} expression The          # determination test condition is true, then the procedure returns a non-zero 0 otherwise
[expression]             # If the condition is true, return 0, otherwise non-zero

the Test  " abc " = " DEF "         # to see the return value echo $? 1 show, because the condition is false
the Test  " abc "  ! = " DEF "        # to see the return value echo $? 0 is displayed, because the condition is true

test -a / tmp ;  echo  $?      # call test to determine / tmp exists and print test the return value
[ -a /tmp] ;  echo  $?       # is exactly equivalent to the above, /tmp definitely exists, so the output is 0

Test cond && cmd1          # determination condition is true when performing cmd1
[cond] && cmd1           # is exactly equivalent to the above
[Cond] && cmd1 || cmd2   # condition is true execute cmd1 otherwise perform cmd2

#Determine whether the /etc/passwd file exists
# Classic statement is to determine if the back of the command returns a value of 0, then, that the condition is true, otherwise false
if test -e /etc/passwd; then
    echo "alright it exists ... "
else
    echo "it doesn't exist ... "
be

# Above fully equivalent, [and the test is the same executable program, but must be the last parameter]
# The name "[" executable generally in / bin or / usr / bin Now, more elegant than test
if [ -e /etc/passwd ]; then   
    echo "alright it exists ... "
else
    echo "it doesn't exist ... "
be

# Is completely equivalent to the above two. In fact, [is already an internal command in the bash era. You can see it with enable
[ -e /etc/passwd ] && echo "alright it exists" || echo "it doesn't exist"

# Value determination variable
if [ "$varname" = "foo" ]; then
    echo "this is foo"
elif [ "$varname" = "bar" ]; then
    echo "this is bar"
else
    echo "neither"
be

# Complex conditional judgment, attention || and && is fully compatible with POSIX recommended wording
if [ $x -gt 10 ] && [ $x -lt 20 ]; then
    echo "yes, between 10 and 20"
be

#You can use the && command connector to do exactly the same thing as above
[ $x -gt 10 ] && [ $x -lt 20 ] && echo "yes, between 10 and 20"

# Parentheses are POSIX XSI and -a -o extended writing, parentheses are literal, to be added in front of the input backslashes
if [ \( $x -gt 10 \) -a \( $x -lt 20 \) ]; then
    echo "yes, between 10 and 20"
be

# You can also use command && connector fully equivalent and do things above
[ \( $x -gt 10 \) -a \( $x -lt 20 \) ] && echo "yes, between 10 and 20"


#Execute if the program exists
[ -x /bin/ls ] && /bin/ls -l

# If you do not consider compatible posix sh and dash these words, can bash unique ((..)) and [[..]]:
https://www.ibm.com/developerworks/library/l-bash-test/index.html


##############################################################################
# Flow control: while / for / case / until
##############################################################################

# while loop
while condition; do
    statements
done

i=1
while [ $i -le 10 ]; do
    echo $i; 
    i=$(expr $i + 1)
done

# for loop: the above while statement is equivalent
for  i  in {1..10} ;  do
    echo $i
done

for name [in list]; do
    statements
done

# for List all files in a directory
for  f  in / home / * ;  die 
    echo $f
done

# bash unique (( .. )) statement, closer to C language, but not compatible with posix sh
for (( initialisation ; ending condition ; update )); do
    statements
done

# Is equivalent to the above
for ((i = 0; i < 10; i++)); do echo $i; done

# case judgment
case expression in 
    pattern1 )
        statements ;;
    pattern2 )
        statements ;;
    * )
        otherwise ;;
esac

# until statement
until condition; do
    statements
done

# select statement
select name [in list]; do
  statements that can use $name
done


##############################################################################
# Command processing
##############################################################################

the Command ls                          # ignore alias directly executable program or built-in command ls
the BUILTIN  cd                          # ignore alias cd built-in command is run directly
enable                              # List all bash built-in command, a command or prohibit
Help {builtin_command}              # View the help of built-in commands (bash built-in command only)

the eval  $ script                        # on the evaluation of the string script variables (execution)


##############################################################################
# Output/input redirection
##############################################################################

CMD1 | cmd2                         # pipelines, cmd1 standard output to the standard input cmd2
< File                              # contents of the file redirect standard input of command
> File                              # will be redirected to the standard output of a command file, overwrite files
>> File                             # standard command to redirect the output to a file, no additional covering
> | File                             # force the output to a file, even if set too: set -o noclobber
n > | File                            # force the file descriptor n redirect the output to a file
<> File                             # use this file as the standard input and standard output
n <> File                            # use as file input and output file descriptors n
n > File                             # redirect output to a file descriptor n
n < File                             # redirect file descriptor n input file content
n > &                                 # standard output dup / merge file descriptor n
n < &                                 # standard input dump / merge oriented descriptors n
n > & m                                # file descriptor is used as a copy descriptor n m of output
n < & m                                # file descriptor is n m as a copy of the descriptor, the input
& > File                              # standard output and standard error redirected to file
< & -                                 # Close standard input
>& -                                 # Close standard output
n >& -                                # Close the file descriptor as output n
n < & -                                # Close the file descriptor as input n
the diff <( CMD1 )  <( CMD2 )                # output compare two orders


##############################################################################
#文字处理- cut
##############################################################################

-C 1-16 Cut                         # intercept the first 16 characters per line
-c 1-16 File Cut                    # interception of a specified file in the first 16 characters per line
-c3- Cut                            # intercept the content of each line beginning at the end of the row from the third character
-d Cut ' : ' -F5                       # taken fifth column contents separated by colons
-d Cut ' ; ' -f2,10                    # taken separated by a semicolon and the tenth column of the second content
-d Cut '  ' -f3-7                     # taken space delimited three to seven
echo "hello" | cut -c1-3           # 显示 hel
echo "hello sir" | cut -d' ' -f2   # 显示 sir
ps | tr -s "  "  | cut -d "  " -f 2,3,4   # cut with tr compressed characters


##############################################################################
# Text Processing - awk / sed
##############################################################################

awk ' {}. 5 Print $ ' File               # print file separated by spaces fifth column
-F awk ' , '  ' {}. 5 Print $ ' File        # fifth column print comma-separated file
awk ' / str / 2} {Print $ ' File         # in the second column of the print file contains all rows str
-F awk ' , '  ' {} of NF Print $ ' File       # prints a comma delimited file last column of each row
awk ' {S}. 1 the END + = $ {S} Print ' File    # count all together in the first column
awk ' NR. 3%. 1 == ' File                  # from the beginning of the first row, every fourth row line is printed

Sed ' S / Find / Replace / ' File          # replacement string appears first in the file, and outputs the result
Sed ' 10s / Find / Replace / ' File        # replace content files, line 10
Sed ' 10,20s / Find / Replace / ' File     # replace lines 10-20 file content
-R & lt Sed ' S / REGEX / Replace / G ' File     # replace all occurrences file
-i Sed ' S / Find / Replace / G ' File      # replace all the characters that appear in the document and the document cover
-i Sed ' / Find / I \ NEWLINE ' File       # before matching text file into a row
-i Sed ' / Find / A \ NEWLINE ' File       # after the matched text file into a row
sed ' /line/s/find/replace/ ' file    # first search for line features and then perform replacement
-e Sed ' S / F / R & lt / ' -e ' S / F / R & lt ' File     # perform multiple replacement
sed ' s#find#replace# ' file #Use          # to replace / to avoid slashes in the pattern
-r -i sed ' S / ^ \ S + G // ' File          # delete the file header spaces per line
sed ' / ^ $ / d ' File                    # delete a file and print blank lines
sed -i ' s/\s\+$// ' file             # delete extra spaces at the end of each line of the file
-n sed ' 2p ' File                    # print the second line of the file
-n sed ' 2,5p ' File                  # second to the fifth line of print files


##############################################################################
# Sort- sort
##############################################################################

File the Sort                           # sort files
-r File the Sort                        # reverse (descending)
-n File the Sort                        # using digital rather than a string compare
-t the Sort: -k 3N / etc / passwd          # sort by the third column of the passwd file
sort -u file                        # Re-sort


##############################################################################
# Quick Jump - https://github.com/rupa/z
##############################################################################

source /path/to/z.sh                # Initialize z.sh in .bashrc
z                                   # List all historical paths and their weights
foo z                               # right to jump to the historical path of the heaviest match foo directory
foo bar z                           # jump to match the weight of history in the path of the largest directories foo and bar right
the -l foo z                            # listed in the directory path and the right of all historical re-match foo
z -r foo                            # According to the highest number of visits, first matching jump
-t foo z                            # according to a recent priority access to match Jump


##############################################################################
# Keyboard bindings
##############################################################################

the bind  ' "\ EH": "\ Cb" '                 # binding ALT + h is the cursor left, with CTRL + b / <Left>
the bind  ' "\ EL": "\ of Cf" '                 # binding ALT + l is the cursor right, with CTRL + f / <Right>
the bind  ' "\ EJ": "\ Cn" '                 # binding ALT + j history for the next article, with CTRL + n / <Down>
the bind  ' "\ EK": "\ Cp" '                 # Bind ALT + k is the history of the strip, with CTRL + p / <Up>
the bind  ' "\ for eH": "\ EB" '                  # binding ALT + H for the cursor one word, with the ALT-b
the bind  ' "\ eL": "\ EF" '                  # binding ALT + L is the cursor right one word, with the ALT-f
the bind  ' "\ eJ": "\ of Ca" '                 # binding ALT + J to move to the beginning of the line, with the CTRL + a / <Home>
the bind  ' "\ eK": "\ of Ce" '                 # binding ALT + K is moved to the end of the line, with the CTRL + e / <End>
the bind  ' "\ E;": "ls -l \ n-" '              # binding ALT +; ls -l command to execute


##############################################################################
# Network Management: ip / ifconfig / nmap ...
##############################################################################

ip a                                #Display all network addresses, same as ip address
A Show eth1 ip                      # display the IP address of the network card
A the Add 172.16.1.23/24 dev eth1 ip    # add the IP address of the network card
A del 172.16.1.23/24 dev eth1 ip    # delete the IP address of the network card
Link Show dev eth0 ip               # display network card device properties
Link ip the SET eth1 up                 # to activate the card
Link ip the SET eth1 Down               # Close card
Link IP SET eth1 MAC address} {      # modify the MAC address
Neighbor ip                        # View ARP Cache
route ip                            # View the routing table
Via the Add 10.0.0.253 route 10.1.0.0/24 ip dev eth0     # Add a static route
route del 10.1.0.0/24 ip            # delete static routes

ifconfig                            # display all cards and interface information
-a ifconfig                         # display all network cards (including the boot did not start) information
eth0 ifconfig                       # specify the information display device
eth0 up ifconfig                    # to activate the card
Down eth0 ifconfig                  # Close card
192.168.120.56 eth0 ifconfig        # Configure an IP address to the network card
10.0.0.8 Netmask 255.255.255.0 up eth0 ifconfig      # Configure IP and start
00 HW ether eth0 the ifconfig: AA: BB: CC: dd: EE             # modify the MAC address

10.0.0.12 nmap                      # scan host port 1-1000
-p 1024-65535 10.0.0.12 nmap        # scanning a given port
10.0.0.0/24 nmap                    # given all hosts within the local area network scanning
-O 10.0.0.12 -sV nmap               # probe hosting and operating system version


##############################################################################
# Interesting command
##############################################################################

hier man                            # view the file system structure and meaning
man the Test                            # View posix sh of conditional aid
ascii man                           # display ascii table
LONG_BIT getconf                    # View system is 32-bit or 64-bit
the bind -P                             # list of shortcuts all bash
Mount | column -t                   # pretty lists the currently loaded file system
ip.cn curl                          # made outside the network ip address and information service providers
the disown -a &&  Exit                   # close all background tasks and exit
CAT / etc / Issue                      # View Linux Release Information
-i Port lsof: 80                     # which applications are using port 80?
-a showkey                          # get key ASCII code
svn diff | view-                   # Use Vim to display colored diff output
filename Music Videos. {Old, new new}               # Fast File rename
Time  the Read                           # use CTRL-D stop, the easiest timing function
file.txt {CP,.} BAK                  # fast backup file
Touch sudo / forcefsck               # forcibly restart in the next scan disk
the Find ~ -mmin 60 The -type f             # to find $ HOME directory, modified files within 60 minutes
wttr.in/~beijing curl               # Check the weather forecast for Beijing
echo  $ {SSH_CLIENT %%  * }              # get you from what IP link to the current host
echo $ [1 + X% the RANDOM]                  # obtain a random number between 1 to X
the bind the -X- ' "\ CI": ls -l '              # Set CTRL + l ls -l command to execute
the Find / The -type f -size + 5M            # find files larger than 5M
--reference f1 f2 chmod             # The f1 and f2 set to exactly the same rights
-L cheat.sh curl                    # Quick Reference Book


##############################################################################
# General Tips
##############################################################################

# Lists the most commonly used commands
history | awk '{a[$2]++}END{for(i in a){print a[i] " " i}}' | sort -rn | head

# List all network states: ESTABLISHED / TIME_WAIT / FIN_WAIT1 / FIN_WAIT2
netstat -n | awk '/^tcp/ {++tt[$NF]} END {for (a in tt) print a, tt[a]}'

# Via SSH to mount the file system
sshfs name@server:/path/to/folder /path/to/mount/point

#Display the top ten running processes and sort by memory usage
ps to | sort -nk +4 | tail

# In the upper right corner of the display clock
while sleep 1;do tput sc;tput cup 0 $(($(tput cols)-29));date;tput rc;done&

# Solutions from the compressed file on the network to a file, and to save the file to avoid intermediate
wget -qO - "http://www.tarball.com/tarball.gz" | tar zxvf -

# Performance Testing: Test processor performance
python -c "import test.pystone;print(test.pystone.pystones())"

# Performance Testing: Memory Bandwidth
dd if=/dev/zero of=/dev/null bs=1M count=32768

# Mount an iso file under Linux
mount /path/to/file.iso /mnt/cdrom -oloop

# To the host via Host A B ssh
ssh -t hostA ssh hostB

#Download all pictures of a website
wget -r -l1 --no-parent -nH -nd -P/tmp -A".gif,.jpg" http://example.com/images

# Quickly create a project directory
mkdir -p work/{project1,project2}/{src,bin,bak}

# Find files by date range
find . -type f -newermt "2010-01-01" ! -newermt "2010-06-01"

#Display the process currently using the network
lsof -P -i -n | cut -f 1 -d " "| uniq | tail -n +2

# Save a file without permission in Vim
:w !sudo tee > /dev/null %

# Load another file .bashrc / .bash_profile (for example, you save the configuration on the github)
source ~/github/profiles/my_bash_init.sh

# Reverse proxy: the external host (202.115.8.1) port (8443) is forwarded to the host within the network 192.168.1.2:443
ssh -CqTnN -R 0.0.0.0:8443:192.168.1.2:443  user@202.115.8.1

#正向Proxy: Forward port 8443 of the local host to 192.168.1.2:443 through 192.168.1.3
ssh -CqTnN -L 0.0.0.0:8443:192.168.1.2:443  user@192.168.1.3

# socks5 Proxy: forward the proxy request of socks5 on the local port 1080 through the remote host
ssh -CqTnN -D localhost:1080  user@202.115.8.1

# Right BackSpace key and the ALT key is provided at the terminal
http://www.skywind.me/blog/archives/2021


##############################################################################
# Useful functions
##############################################################################

# Automatically extract: determine file extensions and call the appropriate decompression command
function q-extract() {
    if [ -f $1 ] ; then
        case $1 in
        * .tar.bz2) tar -xvjf $ 1     ;;
        * .tar.gz) tar -xvzf $ 1     ;;
        *.tar.xz)    tar -xvJf $1    ;;
        *.bz2)       bunzip2 $1     ;;
        * .rar) rar x $ 1        ;;
        *.gz)        gunzip $1      ;;
        *.tar)       tar -xvf $1     ;;
        * .tbz2) tar -xvjf $ 1     ;;
        * .tgz) tar -xvzf $ 1     ;;
        *.zip)       unzip $1       ;;
        *.Z)         uncompress $1  ;;
        *.7z)        7z x $1        ;;
        *)           echo "don't know how to extract '$1'..." ;;
        esac
    else
        echo "'$1' is not a valid file!"
    be
}

# Automatic Compression: judge call the appropriate extension and compression program
function q-compress() {
    if [ -n "$1" ] ; then
        FILE=$1
        case  $ FILE  in
        *.tar) shift && tar -cf $FILE $* ;;
        *.tar.bz2) shift && tar -cjf $FILE $* ;;
        *.tar.xz) shift && tar -cJf $FILE $* ;;
        *.tar.gz) shift && tar -czf $FILE $* ;;
        *.tgz) shift && tar -czf $FILE $* ;;
        *.zip) shift && zip $FILE $* ;;
        *.rar) shift && rar $FILE $* ;;
        esac
    else
        echo "usage: q-compress <foo.tar.gz> ./foo ./bar"
    be
}

# Color CAT beautiful with syntax highlighting, you need to pip install pygments
function  ccat () {
    local style="monokai"
    if [ $# -eq 0 ]; then
        pygmentize -P style=$style -P tabsize=4 -f terminal256 -g
    else
        for  NAME  in  $ @ ;  do
            pygmentize -P style=$style -P tabsize=4 -f terminal256 -g "$NAME"
        done
    be
}


##############################################################################
#好玩的Configuration
##############################################################################

# Into your ~ / .bashrc configuration file, to increase man beautiful color highlights
export LESS_TERMCAP_mb=$'\E[1m\E[32m'
export LESS_TERMCAP_mh=$'\E[2m'
export LESS_TERMCAP_mr=$'\E[7m'
export LESS_TERMCAP_md=$'\E[1m\E[36m'
export LESS_TERMCAP_ZW=""
export LESS_TERMCAP_us=$'\E[4m\E[1m\E[37m'
export LESS_TERMCAP_me=$'\E(B\E[m'
export LESS_TERMCAP_ue=$'\E[24m\E(B\E[m'
export LESS_TERMCAP_ZO=""
export LESS_TERMCAP_ZN=""
export LESS_TERMCAP_se=$'\E[27m\E(B\E[m'
export LESS_TERMCAP_ZV=""
export LESS_TERMCAP_so=$'\E[1m\E[33m\E[44m'

# ALT+hjkl/HJKL quickly move the cursor, add the following content to ~/.inputrc to use all tools,
# Include the use of tools readline bash / zsh / python / lua, to help see: info rluserman
"\eh": backward-char
"\el": forward-char
"\ej": next-history
"\ek": previous-history
"\eH": backward-word
"\eL": forward-word
"\eJ": beginning-of-line
"\eK": end-of-line


##############################################################################
# References
##############################################################################
