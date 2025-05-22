#ft_irc
```
Connecting with netcat:
nc -C <target ip> <port number>
-The -C flag is used to add /r/n at the end of each input. We chose this behaviour due to the behaviour of irssi, which was our main client.
In netcat, the syntax is very strict and all channels in commands should be defined with a "#" at the beginning, and the trailing message must always begin with a ":". Irssi attempts to add these automatically to the message before sending it to the server.
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
KICK #<channel> <user>
INVITE #<channel> <user>
TOPIC #<channel>
MODE #<channel> <flags> <parameters>

Connecting with irssi:
/connect <target ip> <port number> <password> <username(optional)>
Irssi automatically starts a capability communication 
```
