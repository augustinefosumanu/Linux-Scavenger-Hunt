# Linux Scavenger Hunt
<h2> Flag 1 </h2>
<b>Action: </b> To locate the first flag, I used the <b>ls -alt</b> command to list all files and directories (including hidden ones) sorted by their most recent modifications. This helped uncover poorly hidden files, such as a plaintext password list, which contained the flag. <br />
<p align="center">
<img src="https://i.imgur.com/7H7XiFd.png" height="80%" width="90%" alt=""/>

<h2> Flag 2 </h2>
<b>Action: </b> After discovering the exposed user password file in the first task (flag_1), the next logical step is to analyze the shadow file, which stores password hashes. This file should include entries for both the current user and the infamous hacker referenced in flag_2, enabling password-cracking attempts to escalate access. With the hacker’s password successfully cracked using <b>john</b>, I can escalate privileges by logging into their compromised account using <b>su</b> command. This grants access to flag_2, typically stored in the user’s home directory or associated files. <br />
<p align="center">
<img src="https://i.imgur.com/yKkUMtu.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/NcXDHPD.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/5tavKcm.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/cL6GsEW.png" height="80%" width="80%" alt=""/>

<h2> Flag 3 </h2>
<b>Action: </b> Now logged in as the infamous hacker mitnick (via privilege escalation), the hunt for flag_3 begins. First, I’ll audit the <b>/var/log/</b> directory for logs tied to this user using commands like: <b>ls -alt</b>. To unlock the zip file, I’ll craft a compound command to parse the log file, extract all IP addresses, filter for unique entries, and count them. This total becomes the password. Next, I’ll scour mitnick’s directories for zip files referenced in the task using <b>find</b> command. Once found, use unzip to extract contents, which may include logs or clues. <br />
<p align="center">
<img src="https://i.imgur.com/X8Nwb0K.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/cuFQtXU.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/h0dMjs1.png" height="80%" width="80%" alt=""/>

<h2> Flag 4 </h2>
<b>Action: </b> To locate this flag, I will use the ls -alt command to navigate through all directories belonging to the user, listing files and subdirectories in detail. This will help me identify the directory containing the names of all hackers and pinpoint files with read permissions for the owner and executable permissions for everyone else. Once identified, Using the <b>cat</b> command, I will extract the word contained within the stallman file and use it as the password to switch to the stallman user. <br />
<p align="center">
<img src="https://i.imgur.com/x4rcMui.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/rOMQ385.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/MPBrx6J.png" height="80%" width="80%" alt=""/>

<h2> Flag 5 </h2>
<b>Action: </b>  <br />
<p align="center">
<img src="https://i.imgur.com/.png" height="80%" width="80%" alt=""/>

<h2> Flag 6 </h2>
<b>Action: </b>  <br />
<p align="center">
<img src="https://i.imgur.com/.png" height="80%" width="80%" alt=""/>

<h2> Flag 7 </h2>
<b>Action: </b>  <br />
<p align="center">
<img src="https://i.imgur.com/.png" height="80%" width="80%" alt=""/>

<h2> Flag 8 </h2>
<b>Action: </b>  <br />
<p align="center">
<img src="https://i.imgur.com/.png" height="80%" width="80%" alt=""/>
