#ft_irc
```
Connecting with netcat:
nc -C <target ip> <port number>
-The -C flag is used to add /r/n at the end of each input. We chose this behaviour due to the behaviour of irssi,
 which was our main client.
-In netcat, the syntax is very strict and all channels in commands should be defined with a "#" at the beginning,
 and the trailing message must always begin with a ":". Irssi attempts to add these automatically to the message
 before sending it to the server.

Commands for registration (required first):
PASS <server password>
NICK <nickname>
USER <realname> <hostname> <servername> :<username>
QUIT

Additional commands available before registration, but defined only in a minimum way required by irssi:
CAP #<subcommand>
WHO #<channel>
WHOIS <nickname>
PING <origin>

Additional commands available after registration:
PRIVMSG #<channel>/<user>
JOIN #<channel>
KICK #<channel> <user>
INVITE #<channel> <user>
TOPIC #<channel> <new topic(optional)>
PART #<channel>
MODE #<channel> <flags> <parameters>



Connecting with irssi:
/connect <target ip> <port number> <password> <username(optional)>
-Irssi automatically starts a capability communication with the server (CAP->PASS->NICK->USER->CAP) and finds
 the user info from the computer user info.
-The syntax differs from netcat and is more relaxed, but irssi does send the message to the server in the same
 format as netcat

Available commands:
/nick <new nickname>
/quit
/msg <channel>/<user>
/kick <channel(optional)> <user>
/invite <channel(optional)> <user>
/part <channel(optional)>
/topic <channel(optional)> <new topic(optional)>
/mode <channel(optional)> <flags> <parameters>

/ping
-Automatically sent to the server every once in a while to check that the connection
 is still live.
/whois <nickname>
-Automatically sent if the user info is identical to an existing user in order to figure out an alternative
 nickname to use.
/who
-Automatically sent if a user joins a channel in order to find the current users and their statuses
 on the channel.
/mode b
-Automatically sent after successful /join <channel> in order to check the ban list
```
